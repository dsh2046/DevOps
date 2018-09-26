#### Under:  /etc/nginx/sites-available/default AND /etc/nginx/sites-enabled/default

    server {                                                               
        listen      80;                                                    
        server_name 18.191.21.51;                            
        charset     utf-8;                                                 
        client_max_body_size 75M;                                          
        access_log /home/ubuntu/logs/access.log;
        error_log /home/ubuntu/logs/error.log;          
 
        location /static {                                                 
            alias /home/ubuntu/aculink810-device-template-creation/static;                
        }                                                                  
 
        location / {                                                       
            proxy_pass http://127.0.0.1:8000;                              
            proxy_set_header Host $host;
            proxy_pass_header       Authorization;
            proxy_pass_header       WWW-Authenticate;                                   
            proxy_set_header X-Real-IP $remote_addr;                       
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;   
        }                                                                  
    }
