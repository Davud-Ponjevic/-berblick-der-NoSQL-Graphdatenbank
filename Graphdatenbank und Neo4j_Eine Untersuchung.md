# Graphdatenbank und Neo4j: Eine Untersuchung

## Inhaltsverzeichnis
1. [Grundprinzip der Datenstruktur](#1-grundprinzip-der-datenstruktur)
2. [Spezifische Merkmale von Neo4j](#2-spezifische-merkmale-von-neo4j)
3. [Einsatzbereich (Beispiele)](#3-einsatzbereich-beispiele)
4. [Vor-/Nachteile](#4-vorteile-und-nachteile)
5. [Code bzw. Skript-Beispiele](#5-code-bzw-skript-beispiele)

## 1. Grundprinzip der Datenstruktur:

- Graphdatenbanken repräsentieren Daten als Graphen, bestehend aus Knoten (Entitäten) und Kanten (Beziehungen). Neo4j nutzt das Property-Graph-Modell.
- Jeder Knoten und jede Kante können Eigenschaften in Form von Key-Value-Paaren haben.

## 2. Spezifische Merkmale von Neo4j:

- **ACID-Konformität:** Neo4j garantiert die Einhaltung der ACID-Eigenschaften (Atomicity, Consistency, Isolation, Durability).
- **Cypher-Abfragesprache:** Neo4j verwendet Cypher, eine deklarative Abfragesprache, die speziell für die Arbeit mit Graphen entwickelt wurde.
- **Indexierung:** Schnelle Abfragen durch Indexierung von Knoten und Eigenschaften.
- **Transitive Schließung:** Neo4j ermöglicht effiziente Berechnung transitiver Schließungen von Beziehungen.

## 3. Einsatzbereich (Beispiele):

- Soziale Netzwerke: Verbindungen zwischen Benutzern, Freundschaftsbeziehungen.
- Empfehlungssysteme: Analyse von Verhaltensmustern, um personalisierte Empfehlungen zu generieren.
- Netzwerkanalyse: Untersuchung von Beziehungen in komplexen Netzwerken, z.B. in Logistik oder Verkehrsplanung.
- Wissensgraphen: Modellierung von Wissen und semantischen Beziehungen.

## 4. Vor-/Nachteile:

### Vorteile:

- Hohe Leistung bei graphbasierten Abfragen.
- Intuitive Datenmodellierung durch grafische Repräsentation.
- Skalierbarkeit durch horizontalen Datenbank-Cluster.

### Nachteile:

- Nicht optimal für komplexe Abfragen, die keine graphbasierten Muster haben.
- Speicherintensiv bei stark vernetzten Daten.

## 5. Code bzw. Skript-Beispiele:

### Beispiel 1 - Erstellen eines Knotens:

```cypher
CREATE (user:Person {name: 'John', age: 30})

```
### Beispiel 2 - Erstellen einer Beziehung:

```cypher
MATCH (john:Person {name: 'John'}), (jane:Person {name: 'Jane'})
CREATE (john)-[:FRIEND]->(jane)
```
### Beispiel 3 - Abfrage von Beziehungen:

```cypher
MATCH (user:Person)-[:FRIEND]->(friend)
RETURN user.name, friend.name
```