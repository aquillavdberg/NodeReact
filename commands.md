mkdir frontend
mkdir backend

dan losse terminals 1 voor frontend en 1 voor backend

# voor frontend:

cd frontend
npm install create-react-app --global
create-react-app <app_name>
cd <app_name>
npm start

# voor backend:

cd backend
npm init -y
npm i mongodb express cors dotenv

# dan voor basics van mongo db:

- create db:
  use <database_name>;
- create table:
  db.createCollection("<collection_name">);
- insert reconds into collection:
  db.collection_name.insert
  (
  {
  "id" : 1,
  "Name" : "Klaus",
  "Department": "Technical",
  "Organization": "Geeks For Geeks"
  }
  );
- querying a document:
  db.collection_name.find({Name : "Klaus"}).forEach(printjson);

# voor express:

mkdir express
cd express
npm init
npm install express --save

# voor node.js:

mkdir node
cd node
npm init
npm install node --save

# in het algemeen:

aanmaken van een `<name>`.js file (dit is dan de pagina die wordt getoont)
in package.json
"`<functie>`": "node `<name>`.js"
pagina laten laden met npm `<functie>`

http://localhost:3031/
