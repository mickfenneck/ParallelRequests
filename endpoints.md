## **KEY-ENTITIES EXTRACTOR**

#### Endpoints

New or updated endpoints are:
1. text
2. topic

Other endpoints are:
1. '/'
2. meta
3. logo

NB: POST request needed

## Text

Returns a list of dictionary containing entities extracted from the text given and their scores.

    http://localhost:13324/text

Parameters:

- text: text that needs to be analyzed
- nentities: maximum number of entities to extract
- minconf: 
- minlength:
- excludetypes:
- language: language of the given text, default None
- details: set to ['true', '1', 's', 'yes', 'y'] if you desire entities' details

#### example
    
Parameters:

    text: The Mona Lisa is a 16th century oil painting created by Leonardo.
    details: True
    
returns:

    [
      {
        "score": 0.48648648648648646,
        "details": {
          "url": "http://en.wikipedia.org/wiki/Oil_painting",
          "values": [
            "Oil paintings",
            "Oil",
            "Oil on canvas",
            "Art media",
            "Oils",
            "Oil painting",
            "Painting techniques",
            "Painting"
          ],
          "title": "Oil painting"
        },
        "entity": "http://en.wikipedia.org/wiki/Oil_painting"
      },
      {
        "score": 0.25675675675675674,
        "details": {
          "url": "http://en.wikipedia.org/wiki/Leonardo_da_Vinci",
          "values": [
            "People prosecuted under anti-homosexuality laws",
            "16th-century scientists",
            "Italian Renaissance humanists",
            "Leonardo Da Vinci",
            "Italian military engineers",
            "History of anatomy",
            "Members of the Guild of Saint Luke",
            "Italian anatomists",
            "1452 births",
            "Tuscan painters",
            "Da Vinci",
            "Italian physiologists",
            "Renaissance artists",
            "Fabulists",
            "People from the Province of Florence",
            "Mathematics and culture",
            "Giftedness",
            "16th century in science",
            "Renaissance painters",
            "15th-century scientists",
            "Leonardo",
            "15th century in science",
            "Renaissance architects",
            "Physiognomists",
            "Age of Enlightenment",
            "Italian civil engineers",
            "Italian Roman Catholics",
            "Leonardo da Vinci",
            "1519 deaths",
            "Italian inventors",
            "Leonardo da Vinci's",
            "Ballistics experts"
          ],
          "title": "Leonardo da Vinci"
        },
        "entity": "http://en.wikipedia.org/wiki/Leonardo_da_Vinci"
      },
      {
        "score": 0.25675675675675674,
        "details": {
          "url": "http://en.wikipedia.org/wiki/Mona_Lisa",
          "values": [
            "La Gioconda",
            "Monalisa",
            "Mona Lisa",
            "Lisa Giacondo",
            "La Joconde"
          ],
          "title": "Mona Lisa"
        },
        "entity": "http://en.wikipedia.org/wiki/Mona_Lisa"
      }
    ]

## Topic

Returns a dictionary containing the details extracted from the given url.

    http://localhost:13324/topic

Parameters:

- topic: text that needs to be analyzed
- language: language of the given text, default None

#### example
   
Parameters:

    topic: http://en.wikipedia.org/wiki/Big_data
    language: En
    
returns:

    {
      "url": "http://en.wikipedia.org/wiki/Big_data",
      "values": [
        "Big data analytics",
        "Distributed computing problems",
        "Big Data",
        "Big data",
        "Big data analysis",
        "Technology forecasting",
        "Data management",
        "Transaction processing"
      ],
      "title": "Big data"
    }