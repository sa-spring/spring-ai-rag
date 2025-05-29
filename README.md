Spring AI RAG Example
---

Run the application as you would any Spring Boot application. 

```
$ mvn spring-boot:run
```

The first time you run it, it will take a little while to load the document into
the vector store (which will be persisted at /tmp/vectorstore.json). Subsequent
runs will just use the persisted vector store and not try to load the document again.
(This means that if you change the document resource, you'll need to delete
/tmp/vectorstore.json so that it will be reloaded.)

Then you can use `curl` to ask questions:

```
$ curl localhost:8080/ask -H"Content-type: application/json" -d '{"question": "What annotation should I use to create a REST controller?"}'
```

Or with HTTPie it's a little easier:

```
http :8080/ask question="What annotation should I use to create a REST controller?"
```