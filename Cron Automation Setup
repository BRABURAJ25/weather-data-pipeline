ETL in a Management Command

from django.core.management.base import BaseCommand
from forecast.utils import run_etl  # Your reusable ETL function

class Command(BaseCommand):
    help = 'Fetches weather forecast and loads it into the database'

    def handle(self, *args, **kwargs):
        run_etl()
        self.stdout.write("Weather ETL job completed successfully.")

python manage.py fetch_weather
crontab -e
0 7 * * * cd /home/yourusername/weather_etl && /usr/bin/python3 manage.py fetch_weather >> /home/yourusername/weather_etl/logs/cron_etl.log 2>&1
* * * * * cd /home/yourusername/weather_etl && /usr/bin/python3 manage.py fetch_weather >> /home/yourusername/weather_etl/logs/cron_etl.log 2>&1
