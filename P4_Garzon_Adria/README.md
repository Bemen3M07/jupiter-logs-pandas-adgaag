# Exercici 1
### Veure contínuament els logs que es van escrivint a un arxiu
Per veure els logs en temps real, és a dir, a mesura que es van escrivint al fitxer, pots utilitzar la comanda tail amb l'opció -f. Això permet seguir el contingut d'un fitxer a mesura que s'hi afegeixen noves línies.

Comanda:
        **tail -f nom_del_fitxer.log**

- tail: Mostra les últimes línies d'un fitxer.
- -f: Aquesta opció fa que tail es quedi "seguint" el fitxer i mostri qualsevol nova línia que es vagi afegint.

Aquesta comanda és útil per monitoritzar els fitxers de logs en temps real, com quan un servidor o una aplicació està generant nous registres de manera continuada.

### Cercar una paraula concreta dintre d’un arxiu de log
Per cercar una paraula o expressió específica dins d’un fitxer de logs, es fa servir la comanda grep. Aquesta comanda busca una cadena de text dins d'un fitxer i retorna totes les línies que contenen aquesta cadena.

Comanda:
        **grep "paraula_clau" nom_del_fitxer.log**

- grep: Comanda per buscar text dins d'un fitxer.
- "paraula_clau": La paraula o frase que vols cercar.
- nom_del_fitxer.log: El fitxer de logs on es farà la cerca.

Per exemple, si vols cercar totes les línies que contenen l'expressió "error" dins d'un fitxer de logs, utilitzaries la comanda següent:

        **grep "error" fitxer_de_logs.log**

### Cercar amb resultats en temps real
Si vols cercar una paraula o expressió dins d'un fitxer de logs i a més seguir els nous registres, pots combinar tail -f i grep de la següent manera:

        **tail -f nom_del_fitxer.log | grep "paraula_clau"**

Aquesta comanda permet veure en temps real les línies que contenen la paraula "paraula_clau" a mesura que s'afegeixen al fitxer de logs.


# Exercici 2
## Exercici 2-2
### Que creieu que és millor mostrar els logs per exemple a la terminal durant l'execució del programa o bolcar-los en un fitxer de text?
És millor bolcar els logs en un fitxer de text, ja que permet tenir un registre persistent de l'activitat del programa, que pot ser útil per a anàlisis posteriors i per compartir-los amb altres persones. Tot i això, mostrar-los a la terminal és útil per a depuració en temps real, ja que facilita la visualització immediata dels errors o missatges importants mentre s'està executant el programa. Per tant, una combinació d'ambdós mètodes és recomanada, mostrant-los a la terminal per al desenvolupament i guardant-los en un fitxer per a un registre permanent.

## Exercici 2-3
|                                   | **Exemple**                         | **Avantatges**                                          | **Desvantatges**                                                             |
|-----------------------------------|-------------------------------------|---------------------------------------------------------|------------------------------------------------------------------------------|
| **Fent servir la configuració per defecte del mòdul logging** | `logging.basicConfig(level=logging.INFO)`   | - Configuració senzilla i ràpida. <br> - No necessita codi addicional ni configuració extra. | - No ofereix molta flexibilitat per a escenaris complexos. <br> - Poca personalització en el control de logs i el seu maneig. |
| **Instanciant un objecte logger i parametritzat-lo des de programa** | `logger = logging.getLogger('my_logger')` | - Permet configurar els logs de manera més específica. <br> - Major control sobre els handlers i formats. | - Requereix més codi i coneixements. <br> - Pot ser menys convenient per a projectes petits o proves ràpides. |
| **Instanciant un objecte logger a partir d’una configuració emmagatzemada a fitxer** | `logging.config.fileConfig('config.ini')`| - Separació clara entre el codi i la configuració. <br> - Permet modificar els logs sense canviar el codi font. <br> - Ideal per a entorns de producció. | - Necessita un fitxer de configuració extern. <br> - Pot resultar difícil de mantenir si es fa servir un gran nombre de configuracions. |

## Exercici 2-4
| **Informació general**                 | **Llenguatge 1**                         | **Llenguatge 2**                      | 
|----------------------------------------|------------------------------------------|---------------------------------------|
| **Llenguatge**                         | Python                                   | Java                                  | 
| **Nom de la llibreria**                | Loguru                                   | Log4j                                 | 
| **És nativa del llenguatge?**          | No                                       | No                                    | 
| **URL per descarregar-se la llibreria**| [Loguru a GitHub](https://github.com/Delgan/loguru) | [Log4j a Apache](https://logging.apache.org/log4j/)  | 
| **Inicialització de l'objecte logger** | `from loguru import logger`              | `import org.apache.logging.log4j.LogManager;`<br>`Logger logger = LogManager.getLogger(MyClass.class);` | 
|**Nivells de log disponibles**          |  TRACE, DEBUG, INFO, SUCCESS, WARNING, ERROR, CRITICAL | TRACE, DEBUG, INFO, WARN, ERROR, FATAL | 
| **Mètode per fer log**                 | `logger.debug("Missatge")`               | `logger.info("Missatge")`             | 
| **Tipus de manejadors disponibles**    | Pantalla, fitxer, JSON (sèries)          | Pantalla, fitxer, consola, xarxa      | 
| **Opcions de format**                  | Preconfigurat, format JSON, personalització amb `add()` | Format customizable mitjançant XML o JSON | 

