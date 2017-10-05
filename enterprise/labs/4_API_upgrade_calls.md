curl -u andrescruzat:cloudera 'http://localhost:7180/api/version'
v17

curl -u andrescruzat:cloudera 'http://localhost:7180/api/v17/cm/version'
{
  "version" : "5.12.1",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170818-0807",
  "gitHash" : "9bdee611802535491d400e03c98ef694a2c77d0a",
  "snapshot" : false
}[

curl -u andrescruzat:cloudera 'http://localhost:7180/api/v17/users'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "andrescruzat",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}

curl -u andrescruzat:cloudera 'http://localhost:7180/api/v17/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
