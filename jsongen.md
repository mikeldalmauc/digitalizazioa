Following the - generation example create a JSON with the next fields:
 
 - dimensions (in milimeters)
   - x
   - y
   - z
 - address 
    - cities must be in the following list 
        Beasain
        Errenteria
        Hernani
        Hondarribia
        Irun
        Legazpi
        Legorreta
        Ordizia
        Orio
        Zumarraga
        Tolosa
        Donostia
    - state 
        Gipuzkoa
 - telephone (with a format like +34 6xx xxx xxx )
 - weight
 - entregatze-data ( date after today)

generation example: 
[
  '{{repeat(5, 7)}}',
  {
    _id: '{{objectId()}}',
    index: '{{index()}}',
    guid: '{{guid()}}',
    isActive: '{{bool()}}',
    balance: '{{floating(1000, 4000, 2, "$0,0.00")}}',
    picture: 'http://placehold.it/32x32',
    age: '{{integer(20, 40)}}',
    eyeColor: '{{random("blue", "brown", "green")}}',
    name: '{{firstName()}} {{surname()}}',
    gender: '{{gender()}}',
    company: '{{company().toUpperCase()}}',
    email: '{{email()}}',
    phone: '+1 {{phone()}}',
    address: '{{integer(100, 999)}} {{street()}}, {{city()}}, {{state()}}, {{integer(100, 10000)}}',
    about: '{{lorem(1, "paragraphs")}}',
    registered: '{{date(new Date(2014, 0, 1), new Date(), "YYYY-MM-ddThh:mm:ss Z")}}',
    latitude: '{{floating(-90.000001, 90)}}',
    longitude: '{{floating(-180.000001, 180)}}',
    tags: [
      '{{repeat(7)}}',
      '{{lorem(1, "words")}}'
    ],
    friends: [
      '{{repeat(3)}}',
      {
        id: '{{index()}}',
        name: '{{firstName()}} {{surname()}}'
      }
    ],
    greeting: function (tags) {
      return 'Hello, ' + this.name + '! You have ' + tags.integer(1, 10) + ' unread messages.';
    },
    favoriteFruit: function (tags) {
      var fruits = ['apple', 'banana', 'strawberry'];
      return fruits[tags.integer(0, fruits.length - 1)];
    }
  }
]

https://json-generator.com/

[
  '{{repeat(5, 7)}}',
  {
    "id": "{{objectId()}}",
    "dimensions": {
      "x": "{{integer(100, 1000)}}",
      "y": "{{integer(100, 1000)}}",
      "z": "{{integer(100, 1000)}}"
    },
    "address": {
      "Adress": '{{integer(1, 50)}} {{integer(1, 5)}}-{{random("A", "B", "C", "D")}}, {{street()}}',
      "city": '{{random("Beasain", "Errenteria", "Hernani", "Hondarribia", "Irun", "Legazpi", "Legorreta", "Ordizia", "Orio", "Zumarraga", "Tolosa", "Donostia")}}',
      "state": "Gipuzkoa"
    },
    "telephone": "+34 6{{integer(10, 99)}} {{integer(100, 999)}} {{integer(100, 999)}}",
    "weight": '{{floating(1, 25, 2)}}',
    "entregatze-data": "{{date(new Date(Date.now() + 24 * 60 * 60 * 1000), new Date(Date.now() + 30 * 24 * 60 * 60 * 1000), 'YYYY-MM-dd')}}"
  }
]