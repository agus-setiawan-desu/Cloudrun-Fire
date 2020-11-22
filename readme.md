# pastikan node tersedia 

npm install

# enable this API 
Cloud Run Admin API


--> pastikan sudah membuat project di firebase console (jangan buat project dari GCP)
--> upgrade ke pas as you go
--> masuk ke GCP --> import project dari firebase 
--> APIs & services --> Library --> lalu enable Cloud Run Admin API 

# login dari terminal
gcloud auth login 

gcloud init

--> pilih firebase project
# cd ke server
gcloud builds submit --tag gcr.io/flask-hosting-abdf8/cloudrun-fire

flask-hosting-abdf8 = nama project di firebase
cloudrun-fire = nama untuk image docker nya 

gcloud run deploy --image gcr.io/flask-hosting-abdf8/cloudrun-fire

# cd to root (bagian luar)

npm i -D firebase-tools

firebase init

--> pilih hosting
--> folder namanya static --> semua klik No
--> delete index.html dan 404.html

firebase serve

--> running di local

firebase deploy --only hosting

--> untuk hosting

# kalau mau deploy cepat 
gcloud run deploy cloudrun-fire --region us-central1 --platform managed --image gcr.io/flask-hosting-abdf8/cloudrun-fire