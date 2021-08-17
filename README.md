# medblog

## The main function:
- Articles, page, classified catalog, tag added, delete, editing, etc. Articles and page supports `markdown`, support code highlight.
Support article full-text search.
- Complete comment function, including post reply comments, and email reminder, support` Markdown`.
- Side bar function, latest article, maximum reading, tag cloud, etc.
- Support OAuth landing, there is already Google, GitHub, Facebook, Weibo, QQ login.(google and facebook are not working due to callback url issue )
- Support `Memcache` Cache, support cache automatic refresh.
- Simple SEO function, new articles, etc. will automatically notify Google and Baidu.
- Integrated simple graphics feature.
- Integration` Django-compressor`, automatic compression` CSS`, `js`.
- Website exception email reminder, if there is no captured exception, a reminder message is automatically sent.

## Installation

Install using PIP: `Pip Install -ur Requirements.txt`



`bin` Directory is in the` linux` environment using `nginx` +` gunicorn` + `Virtualenv` +` supervisor` to deploy script and `nginx` configuration file


## Run

 Modify `Medgloss / Setting.py` Modify the database configuration, as shown below:

`` `python
Databases = {
    'Default': {
        'Engine': 'Django.db.backends.mysql',
        'Name': 'medblog',
        'User': 'root',
        'Password': 'Password',
        'Host': 'Host',
        'Port': 3306,
    }
}
`` `

### Creating a database
Implementation in the mysql database:
`` `SQL
Create Database `medblog` / *! 40100 Default Character Set UTF8MB4 Collate UTF8MB4_UNICODE_CI * /
`` `

Then execute under the terminal:
`` ``
./manage.py makemigrations
./manage.py migrate


### Creating a super user

 Under the terminal:
`` ``
./manage.py createSuperuser
`` `

### Create test data
Under the terminal:
`` ``
./manage.py create_testdata
`` `

### Collect static files
Under the terminal:
`` ``
./manage.py collectionstatic --noinput
./manage.py compress --force
`` `

### start operation:
Perform: `./manage.py runserver`


