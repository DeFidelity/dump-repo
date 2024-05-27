Start Redis:
sudo service redis-server start

Redis Status:
sudo service redis-server status

Start Celery:
celery -A sherlock_rest_service worker -l INFO


add fly.io to path:

export FLYCTL_INSTALL="/home/defideh/.fly"
  export PATH="$FLYCTL_INSTALL/bin:$PATH"


ubuntu:
export FLYCTL_INSTALL="/home/defidelity/.fly"
  export PATH="$FLYCTL_INSTALL/bin:$PATH"


You could delete it by typing sudo rm -rf {dir_name}. The directory might have been set to read-only permission. I hope the given command can delete the folder.


linux

curl -L https://fly.io/install.sh | sh
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1735    0  1735    0     0   1201      0 --:--:--  0:00:01 --:--:--  1201
######################################################################## 100.0%
set update channel to shell
flyctl was installed successfully to /home/defidelity/.fly/bin/flyctl
Manually add the directory to your $HOME/.bash_profile (or similar)
  export FLYCTL_INSTALL="/home/defidelity/.fly"
  export PATH="$FLYCTL_INSTALL/bin:$PATH"
Run '/home/defidelity/.fly/bin/flyctl --help' to get started
