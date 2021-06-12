

## blog-api
Blog API project built using Django Rest Framework, with the following models: Post, Comment, Postlike, Commentlike 

![drf image](https://www.thetestspecimen.com/img/django-initial/django-rest-logo-1920w.jpg)

## authentication schemes used:
    1- BasicAuthentication
    2- SessionAuthentication
    3- TokenAuthentication

### 1- perform crud operations with **BasicAuthentication**:
    ##################### create new instance #########################
    http -a yourusername localhost:8000/book/ title='book title' 
    ##################### edit an instance #########################
    http -a yourusername PUT localhost:8000/book/1/ title='book title edited' 
    ##################### fetch all instances #########################
    http localhost:8000/book/  
    ##################### fetch one instance #########################
    http localhost:8000/book/1/ 
    ##################### delete an instance #########################
    http -a yourusername DELETE localhost:8000/book/1/  


### 2- perform crud operations with **SessionAuthentication**:
    use the borwsable API to login then use HTML form or Row data


### 3- perform crud operations with **TokenAuthentication**:

    step 1: **obtain auth token**
        http POST localhost:8000/obtain-auth-token/ username='yourusername' password='yourusernamepassword'
        {
            "email": "yourusername@gmail.com",
            "token": "efa0b636c8325dcd8d5aacd6f45f00c6606274a",
            "user_id": 1,
        }

    step 2: **make post request with the Token **
        http localhost:8000/book/ title='another book title' "Authorization: Token efa0b636c8325dcd8d5aacd6f45f00c6606274a"
        {
            "id": 11,
            "owner": "yourusername",
            "title": "book 12",
        }


