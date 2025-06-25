To Set Up Django App

django-admin startproject weather_etl
cd weather_etl
python manage.py startapp forecast

To Create Weather Model

from django.db import models

class WeatherRecord(models.Model):
    city = models.CharField(max_length=100)
    date = models.DateField()
    temperature = models.FloatField()
    humidity = models.IntegerField()
    description = models.CharField(max_length=255)

    def __str__(self):
        return f"{self.city} - {self.date}"


ETL Code in Django

import requests
from datetime import datetime
from .models import WeatherRecord

API_KEY = "your_api_key"
CITIES = ["Chennai", "Mumbai", "Delhi"]

def run_etl():
    for city in CITIES:
        url = f"http://api.openweathermap.org/data/2.5/forecast/daily?q={city}&cnt=16&appid={API_KEY}&units=metric"
        response = requests.get(url)
        if response.status_code == 200:
            data = response.json()
            for day in data['list']:
                record_date = datetime.utcfromtimestamp(day['dt']).date()
                WeatherRecord.objects.update_or_create(
                    city=city,
                    date=record_date,
                    defaults={
                        "temperature": day['temp']['day'],
                        "humidity": day['humidity'],
                        "description": day['weather'][0]['description'],
                    }
                )

Create a Django Management Command

from django.core.management.base import BaseCommand
from forecast.utils import run_etl

class Command(BaseCommand):
    help = 'Runs ETL to fetch and store weather data'

    def handle(self, *args, **kwargs):
        run_etl()
        self.stdout.write("Weather ETL completed.")

To Add a View and Template

from django.shortcuts import render
from .models import WeatherRecord

def dashboard(request):
    data = WeatherRecord.objects.all().order_by('-date')[:50]
    return render(request, 'dashboard.html', {'data': data})
