# MERN-on-aws
The repository guides, how to setup a MERN application on aws EC2

THe repo contains a file aws.txt to setup MERN on aws EC2 instance.
Note : The file does not contain information on how to setup native mongoDB on EC2, it is for the users who use connection string to connect with MongoDB, i.e for MONGO ATLAS

### In case you encounter memory error, saying **Javascript heap out of memory** while creating react build, try following methods : 

1. in your package.json in client folder, change react start script from `react-scripts start` to `GENERATE_SOURCEMAP=false react-scripts start`. This can avoid some memory 
consumption.
1. increase nodejs space . run this command to increase the space of you app. `set NODE_OPTIONS=--max_old_space_size=8172`
Yoi can set it to any amount of memory. In this case it is 8gb(8172mb)
1. Increase size taken by react app while build . In package.json file of client , change scripts build line from `react-scripts build` to `react-scripts --max_old_space_size=4096 build`

### Configurng Nginx for file uploading . 
To increase the file transfer size =>

* `cd /etc/nginx/` and open **nginx.conf** file by using `sudo vim nginx.conf`
* Then inside `http {` add this line : `client_max_body_size 100M;`
* After this go to server directory and run `sudo service nginx stop && sudo service nginx start`
* Your max file transfer is increased to 100mb

If you find this useful do star this repository 👀
