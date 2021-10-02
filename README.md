Codigo SPS _PRACTICA

GET log_consultas/_count

GET log_consultas/_mapping

GET log_consultas/_search

GET /_xpack/sql?format=txt
{
  "query":"SELECT estado_consulta FROM log_consultas ORDER BY consultas_realizadas" 
}

GET log_consultas/_search
{
  "query":{
    "match":{
      "estado_consulta":"error"
    }
  }
}

GET log_consultas/_search
{
  "query":{
    "match":{
      "estado_consulta":"consumo"
    }
  }
}

GET log_consultas/_search
{
  "query":{
    "match_phrase":{
      "administrador":"Juan Lara"
    }
  }
}



GET /_xpack/sql?format=txt
{
  "query":"SELECT SUM(consultas_realizadas) FROM log_consultas WHERE estado_consulta='error'" 
}





