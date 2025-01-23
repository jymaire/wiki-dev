# Couches

## Controleur

Gestion des accès, recevoir les données et les valider. Passe plat vers un service

## Service

Implémentation des règles métiers

## Mapper

Transformation des données.
Pas de logique métier dedans ou d'appels à des services/repositories !

## Repository

Interaction avec les sources de données

# Test

## Test unitaire

Test des règles métiers, des cas aux limites

## Test d'intégration

Vérifier que les différentes couches s'interfacent bien

## Test end to end

Reproduction de scénarios utilisateurs complets
