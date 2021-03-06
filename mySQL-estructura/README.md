# We will model several entity-relationship diagrams.
# 2.1: MySQL data structure

## Level 1
### - Exercise 1 - Optics
An optician called Cul d'Ampolla wants to computerize customer management and the sale of glasses:

First of all the optician wants to know which is the supplier of each of the glasses. Specifically, you want to know the name, address (street, number, floor, door, city, postal code and country) of each provider, telephone, fax, NIF.

The optical purchasing policy is based on the fact that glasses from one brand will be bought from a single supplier (so you can get better prices), but they can buy glasses from several brands from one supplier. From the glasses you want to know, the brand, the graduation of each of the glasses, the type of frame (floating, paste or metal), the color of the frame, the color of the glasses and the price.

Customers want to store their name, mailing address, phone number, email, and registration date. We are also asked, when a new customer arrives, to store the customer who has recommended the establishment (as long as someone has recommended it). Our system will need to indicate who and when the employee has sold each pair of glasses.


### - Exercises 2 - Pizzeria
A customer has hired you to design a website that allows you to place food orders online:

Please note the following instructions for modeling the project database: We store a unique identifier for each client, first name, last name, address, zip code, location, province, and phone number. Location and province data will be stored in separate tables. We know that a locality belongs to a single province, and that a province can have many localities. For each location we store a unique identifier and a name. We store a unique identifier and name for each province.

A customer can place many orders, but a single order can only be placed by a single customer. Each order stores a unique identifier, date and time, if the order is for home delivery or in-store collection, the number of products selected for each type and the total price. An order may consist of one or more products.

Products can be pizzas, burgers and drinks. Each product is stored: a unique identifier, name, description, image and price. In the case of pizzas, there are several categories that can change their name throughout the year. A pizza can only be in one category, but one category can have many pizzas.

A unique identifier and a name are stored for each category. An order is handled by a single store, and one store can handle many orders. Each store has a unique identifier, address, zip code, location, and province. Many employees can work in one store and one employee can only work in one store. Each employee is stored a unique identifier, name, surname, nif, telephone and whether he works as a cook or delivery man. For home delivery orders, it is important to save the delivery person who delivers the order and the date and time of delivery.

## Level 2
### - Exercise 1 - Youtube
We'll try to make a simple model of what the database would look like for a reduced version of YouTube:


De cada usuari guardem un identificador ??nic, email, password, nom d'usuari, data de naixement, sexe, pa??s, codi postal. Un usuari publica v??deos. De cada v??deo guardem un identificador ??nic, un t??tol, una descripci??, una grand??ria, el nom de l'arxiu de v??deo, durada del v??deo, un thumbnail, el nombre de reproduccions, el n??mero de likes, el n??mero de dislikes.

Un v??deo pot tenir tres estats diferents: p??blic, ocult i privat. Un v??deo pot tenir moltes etiquetes. Una etiqueta s'identifica per una Identificador ??nici un nom d'etiqueta. Interessa guardar qui ??s l'usuari que publica el v??deo i en quina data/hora el fa. Un usuari pot crear un canal. Un canal t?? un identificador ??nic, un nom, una descripci?? i una data de creaci??. Un usuari es pot subscriure als canals d'altres usuaris. Un usuari pot donar-li un like o un dislike a un v??deo una ??nica vegada. Caldr?? portar un registre dels usuaris que li han donat like i dislike a un determinat v??deo i en quina data/hora ho van fer. Un usuari pot crear playlists amb els v??deos que li agraden. Cada playlist t?? un identificador ??nic, un nom, una data de creaci??, i un estat que indica que pot ser p??blica o privada. Un usuari pot escriure comentaris en un v??deo determinat.

Cada comentari est?? identificat per un identificador ??nic, el text del comentari i la data/hora en la qual es va realitzar. Un usuari pot marcar un comentari com m'agrada o no m'agrada. Caldr?? portar un registre dels usuaris que han marcat un comentari com m'agrada/no m'agrada, i en quina data/hora ho van fer.

## Nivell 3
### - Exercici 1 - Spotify
Provarem de fer un model senzill de com seria la base de dades necess??ria per a Spotify:

Existeixen dos tipus d'usuaris: usuari free i usuari premium. De cada usuari guardem un identificador ??nic, email, password, nom d'usuari, data de naixement, sexe, pa??s, codi postal.

Els usuaris premium realitzen subscripcions. Les dades necess??ries que caldr?? guardar per a cada subscripci?? s??n: data d'inici de la subscripci??, data de renovaci?? del servei i una forma de pagament, que pot ser mitjan??ant targeta de cr??dit o PayPal.

De les targetes de cr??dit guardem el n??mero de targeta, mes i any de caducitat i el codi de seguretat. Dels usuaris que paguen amb PayPal guardem el nom d'usuari de PayPal. Ens interessa portar un registre de tots els pagaments que un usuari premium ha anat realitzant durant el per??ode que est?? subscrit. De cada pagament es guarda la data, un n??mero d'ordre (que ??s ??nic) i un total.

Un usuari pot crear moltes playlists. De cada playlist guardem un t??tol, el nombre de can??ons que cont??, un identificador ??nic i una data de creaci??. Quan un usuari esborra una playlist no s'esborra del sistema, sin?? que es marca com que ha estat eliminada. D'aquesta manera l'usuari pot tornar a recuperar els seus playlists en cas que les hagi eliminat per error. ??s necessari emmagatzemar la data en la qual uneixi playlist ha estat marcada com eliminada.

Podem dir que existeixen dos tipus de playlists: actives i esborrades. Una playlist que est?? activa pot ser compartida amb altres usuaris, aix?? vol dir que altres usuaris poden afegir can??ons en ella. En una llista compartida ens interessa saber quin usuari ha estat el que ha afegit cada can???? i en quina data ho va fer. Una can???? nom??s pot pert??nyer a un ??nic ??lbum. Un ??lbum pot contenir moltes can??ons. Un ??lbum ha estat publicat per un ??nic artista. Un artista pot haver publicat molts ??lbums. De cada can???? guardem un identificador ??nic, un t??tol, una durada i el nombre de vegades que ha estat reprodu??da pels usuaris de Spotify.

De cada ??lbum guardem un identificador ??nic, t??tol, any de publicaci?? i una imatge amb la portada. De cada artista guardem un identificador ??nic, nom i una imatge de l'artista. Un usuari pot seguir a molts artistes. Un artista pot estar relacionat amb altres artistes que facin m??sica semblant. De manera que Spotify pugui mostrar-nos un llistat d'artistes relacionats amb els artistes que ens agraden. Tamb?? ens interessa guardar quins s??n els ??lbums i les can??ons favorites d'un usuari. Un usuari pot seleccionar molts ??lbums i moltes can??ons com a favorites. 

Per verificar el teu disseny, omple les taules amb dades de prova per tal de verificar que les relacions s??n correctes i efectua les seg??ents consultes i comprova'n els resultats:

## Verificaci??
### Optica:
Llista el total de factures d'un client en un per??ode determinat
Llista els diferents models d'ulleres que ha venut un empleat durant un any
Llista els diferents prove??dors que han subministrat ulleres venudes amb ??xit per l'??ptica

### Pizzeria:
Llista quants productes de la categoria 'begudes' s'han venut en una determinada localitat
Llista quantes comandes ha efectuat un determinat empleat
