sudo usermod -aG docker jenkins

sudo systemctl restart jenkins

groups jenkins

sudo chown root:docker /var/run/docker.sock
sudo chmod 660 /var/run/docker.sock

sudo systemctl start docker
sudo systemctl enable docker


sudo docker build . -t flask-app:latest
sudo docker run -d -p 6000:6000 flask-app:latest


sudo chown root:docker /var/run/docker.sock
sudo chmod 660 /var/run/docker.sock

sudo apt update
sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx -d app1.aseemcloudtech.com
