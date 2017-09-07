# SWAPI-Java REST Client

The [SWAPI (Star Wars API)](https://swapi.co/) client for Java

## How to use it

```java
public static void main(String[] args)
    {
        StarWarsApi.init();
        StarWars api = StarWarsApi.getApi();

        api.getAllFilms(1, new Callback<SWModelList<Film>>() {
            @Override
            public void success(SWModelList<Film> filmSWModelList, Response response) {
                System.out.println("Count:"+ filmSWModelList.count);
                for(Film f : filmSWModelList.results) {
                    System.out.println("Title:" + f.title);
                }
            }

            @Override
            public void failure(RetrofitError error) {

            }
        });


    }
```

## How to run sample app
```
mvn test
```
