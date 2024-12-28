<<code src:"sudo ln -s /etc/nginx/sites-available/mywebsite /etc/nginx/sites-enabled/" language:"bash" caption:"creating the link">>

<<code src:"sudo nginx -t" language:"bash" caption:"test the config">>

<<code src:"sudo systemctl reload nginx" language:"bash" caption:"reload NginX">>
