# test-fastapi2
local ubuntu or docker

# Ubuntu
///set up///
-create env:
    python3 -m venv test-fastapi 
- run env:
    source test-fastapi/bin/activate
- install requirements.txt:
    pip install -r requirements.txt
- copy file nginx-local.conf to /etc/nginx/nginx.conf
- copy file default-local to /etc/nginx/sites-enabled/default

/// run 2 server ///
    uvicorn main:app1 --reload --port 8000
    uvicorn main:app2 --reload --port 8080
    sudo service nginx restart
# Khoi chay tren docker
docker-compose --file docker-compose.yml up <nếu muốn có cache>
docker-compose --file docker-compose.nocache.yml up <nếu ko muốn có cache>
