# Supervisor
#### Do not use 'apt install supervisor',   Use 'pip install supervisor'
1. Create folder /etc/supervisor/conf.d
   and file /etc/supervisor/supervisord.conf
   
2. Run command(with su): echo_supervisord_conf > /etc/supervisor/supervisord.conf

3. Configure files

4. sudo supervisord -c /etc/supervisor/supervisord.conf

5. If files changed, run: sudo supervisorctl reload

