Pokedex
===

## Code Wars

* Complete [today's Kata](https://www.codewars.com/kata/insert-dashes).
* Complete [Day Two Kata](https://www.codewars.com/kata/simple-validation-of-a-username-with-regex)

## App

Build a searchable, sortable pokemon viewer. The lab includes the pokemon data you can use.

Basic structure is like:

```sh
+-------------------------+
|  Filter and Sort        |
+-------------------------+
|      Results            |
|◼️◻️◻️◼️◻️◻️◻️◻️◼️◻️◻️              |
|◻️◻️◼️◻️◻️◼️◻️◻️◼️◻️◻️              |
|◻️◻️◼️◻️◻️                    |
|                         |
+-------------------------+
```

## Components

```sh
App
 |
 +-- Header
 |    |
 |    +-- Filter
 |    |
 |    +-- Sort
 |
 +-- Results
      |
      + Tile
```

### App

Top-level container. Will mediate between Filter/Sort in Header and Results.

#### Header

Container for Filter and Sort

##### Filter

Offers controls for filtering. At a minimum allow:

* Filtering based on type (notice there are two possible matches for each pokemon). Use the source data to derive list of types. Check out `Set` for deduplication. (HINT: getting values out of a Set: `[...set.values()]`)
* Pick at least one quantified attribute (attack, defence, etc.) and allow user to enter a minimum value. Make sure your input only allows whole, positive integer values.

##### Sort

Offer sorting based one of:

1. Pokemon name (default)
1. Type (use `type_1`)
1. Attack
1. Defence

#### Results

Receives the filtered and sorted results from app and generates `Tile` components.

##### Tile

Displays a pokemon image, name and relevant data (attack, defence, anything you used in filter/sort). Color code based on type. Feel free to put other attributes.

## Rubric

* Correct overall structure and organization **1pt**
* `Filter` and `Sort` components **3pts**
* `Results` and `Tile` components **3pts**
* Managing data (apply filter and sort) using computed properties **3pts**
