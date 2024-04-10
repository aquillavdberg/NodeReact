@npm start

# "backend"

## in (root) package.json

"main": "`<file>`.js",

in dit geval "app.js"

"scripts": {

    "start": "`<functie>`",

in dit geval  "node app",

## in (root) app.js

(deze app.js staat in dezelfde directory als de package.json)

    constServer = require('./models/server');

## (models/)server.js

(deze zit in het mapje models en die zit weer in dezelfde map als app.js)

bind middelwares:

    express.static(path.join(__dirname, "../client/build"))

en routes:

    this.app.use(this.paths.auth, require("../routes/auth"));

    this.app.use(this.paths.homepage, require("../routes/homepage"));

en anders:

    path.join(__dirname, "../client/build/index.html")

## (client/)build.index.html

bevat like skelet voor html en idk, iets met js scripts /aanmaken vd script elements

## (routes/)auth.js & homepage.js

deze linken weer door: ze geven de *routes* naar het volgende.

    const { getArtworks } = require("../controllers/homepage");

    const { check } = require('express-validator');

    const { validateInput } = require('../middleware/validate-input');

    const { login } = require('../controllers/auth');

## (middelware/)validate-input.js

deze checkt of er wel input is

## (controllers/)auth.js & homepage.js

bij auth.js als t goed gaat:

  res.json({

    name:"Test User",

    token:"A JWT token to keep the user logged in.",

    msg:"Successful login",

bij homepage.js

koppelt art source:

    constAIC_URL = "https://api.artic.edu/api/v1/artworks/search?q=";

maakt search mogelijk

    `${AIC_URL}${keyword}&limit=15&fields=id,title,image_id,date_display,artist_display,place_of_origin,medium_display`,


# "frontend"

build => statics, de html daarin is het 1e wat er gebruikt wordt

public => bevat template html (good to know)

src bevat eigg de hele website

(client/src/)index.js roept ()client/src/)app.js

## (client/src/)app.js

deze houdt het overzicht


linkt naar de benodigde files:

    import Login from"./components/login";

    import Homepage from"./components/homepage";



gebruikt functionaliteiten vanuit de benodigde files:

    (isUserSignedIn &&`<Homepage onLogout={onLogout}/>`) || (`<Login onLoginSuccessful={onLoginSuccessful}/>)`

## (client/src/components) login & homepage

hierin zitten de webpages.

deze bevatten de html en functionaliteiten voor buttons e.d.

# overig

## nog uitzoeken

Hoe kom je van auth naar homepage?
