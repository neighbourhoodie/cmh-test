Start web server

```
cd cmh-test
python -m http.server
```

Other terminal, start proxy:

```
cd cmh-test
node bin/proxy
```

this assumes your local dev server runs on port 8000. edit `bin/proxy` line 32 if it lives elsewhere

1. In the browser, go to http://127.0.0.1:1337 and open the dev tools console
2. Then enter username and password and hit [login]
  - see a success message in the console
3. hit the [replicate] button, see PouchDB-usual logs

To look at the remote CouchDB Fauxton, do:

```
npm i -g fauxton
fauxton -c https://onefleet.backend.lol/_api/ -p 1336
```

Then in the browser, go to http://127.0.0.1:1336

To get the CouchDB admin password, send me your SSH key.
 
Then:

```
ssh root@onefleet.backend.lol cat src/couchdb-mini-hosting/.env | grep COUCHDB_PASS
```
