#### SIFU
###### General

Sifu is a an API that handles the creation of base notebooks for a course, and
the provisioning and running user notebooks and environments.

Sifu should run alongside jupyter notebook server in a docker image.

Future changes to Sifu will include management of the notebook server itself,
setting up remote synchronization between the docker file system where ephemeral
copies of a user's notebook is stored, and a remote store such as Amazon S3.

###### Usage:

```py
GET  'v1/api/notebooks/courses/files/' # Check if base file exists
POST 'v1/api/notebooks/courses/files/' # Create base file

GET  'v1/api/notebooks/users/:username/courses/:course/files/:file' # (Server user notebook) Return redirect for embedding notebook in iframe
GET  'v1/api/notebooks/users/courses/files' # Check if user notebook exists
POST 'v1/api/notebooks/users/courses/files/' # Create user notebook
```

#### Run with Puma as production server
```bash
RAILS_ENV=production bundle exec puma -C /sifu/config/puma.rb /sifu/config.ru
```

###### TODO

1. Write tests for api calls
2. Manage jupyter server directly
3. Manage remote store of notebooks
4. Add support for deleting notebooks locally (and NB remotely)
5. ~~integrate oAuth2 support~~
6. Prevent access to jupyter notebook through anything except Sifu
7. Look at supporting multipart uploads to Sifu instead of current payload

```text
MMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMM$OZ$7MMMMMMMMMMMMMMMN$$$MMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMOZ8OO$OMMMMMMMMMMMN?$8OZMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMZO7ZO$7+MMMMMMMMM~+$Z7ZMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMM$I$O8DZI~MMMMMMM,,?ZOIZMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMOO87MMMM~$Z8DN8+~~,.,...+8OO+MMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMDMN??ZMM8?$ZOIO+::,,,,,:+$ZIMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMZZ$Z$$M$:I:,.,,:::=+~~~,.:MMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMZO8OO$$$M..,.~OOOOO=+=~ZZ+~MMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMZOZ88OZ$=,:,~O8=+~NO778N~DZ=OMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMOZZ888OOI:~:OOO~Z,=Z:=O~I8O$ZMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMN888O~=+$Z$$$$7:.=I7$7Z+MMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMM88ZI?=+I$7=IIZ$7+===7DOMMMMMMMMMMO8MMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMM88$$7I??+7==~=777DD88OZMMMMMMMMDMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMMMOZOO$$Z77I77NDDN8D8$$$77$$7~8OMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMMMNOZON$77$+NDDD8D8D8OZZ$$Z$I8OOMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMMMMOZ$ONNNDDDD8888DDDDOOOOOIIZDOMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMMMMOZOD8OO888888NDNDN8$D8OO7ZZD8MMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMMMMMN8O8DD888D88DDNDDDO$MD8OOZDDMMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMMMMMNDDD888DDDOOO88DDNDD8..,ZZD8MMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMNNDDDD8888OODDOO88OOO77?+=~?MMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMNNNDDDNZOOOZZZZZOO888OO$I==MMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMMMMM$$$ODDD88OOZZZZZZOZOZZ8N$OZ7=NMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMMZ7$ZZZ888DDDD8888OOOOZZZZZDNDZZ+MMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMDND8$ZZOOOO88888888OZZOOZO$ZDDDNIMMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMM8DDNNDD8OOOOOOOOOOOOOOZOZ$ZODDD$7DMMMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMMDD8Z$ZMNDDNDNDDDDNDNDDNDDDNDDZ77I$MMMMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMMMMD8$$ZMMMMMMMMMMMMMMNOZ$IZNDOO77I7?MMMMMMMMMMMMMMMMM
MMMMMMMMMMMMMMMMMMMMMMMMMMMMMDDDNNMMMMMMMMMMMMMMMMMMMMMMMMZ?+$ZOMMMMMMMMMMMMMMMM
```

