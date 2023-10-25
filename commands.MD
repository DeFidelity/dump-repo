Start Redis:
sudo service redis-server start

Redis Status:
sudo service redis-server status

Start Celery:
celery -A sherlock_rest_service worker -l INFO


add fly.io to path:

export FLYCTL_INSTALL="/home/defideh/.fly"
  export PATH="$FLYCTL_INSTALL/bin:$PATH"
