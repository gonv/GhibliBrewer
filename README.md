# GhibliBrewer
Transform your R plots with palettes inspired by the beautiful visuals of Studio Ghibli movies!

This package was based on coding from the [MetBrewer](https://github.com/BlakeRMills/MetBrewer) package. 
All original images belong to Studio Ghibli (CC-licensed), and can be accessed through their [website](https://www.ghibli.jp/works/).

This package was equally developed by Gonzalo Borrego-Yaniz and Javier Martínez-López. For requests, questions and comments, feel free to reach out to us!
* Twitter: [Javi](https://twitter.com/javiml221098)   [Gonzalo](https://twitter.com/gonzaloyaniz)

# Instalation
GhibliBrewer is a R package that can be installed via github.

```
install.packages("devtools")

devtools::install_github("goboru/GhibliBrewer")
```

# Usage
**Create a palette:**
```
palette <- glibli.brewer("Howl-Castle")
palette <- glibli.brewer(palette="Totoro-Mouth", direction="default", type="discrete", n=5)
```
* palette: String, name of the palette
* direction: "default", "reverse" or "random". "default" if not specified.
* type: "discrete" or "continuous". "discrete" if not specified. 
* n: Number of colors, up to the maximum of colors predefined in the palette. Maximun size of the palette by default.


**Display an individual palette:**
```
# Run the glibli.brewer() function without assigning the output to a variable
glibli.brewer(palette="Totoro-Mouth", direction="default", type="discrete", n=5)
```

**Display all palettes:**
```
# All palettes as set by default
display.ghibli()
```
![All](https://github.com/goboru/GhibliBrewer/assets/102520815/f1b88ae4-4384-4168-b3cb-e91d49c3426e)

```
# Display all palettes with a specific number of colors with "n"
display.ghibli(n=4)

# Change the direction of the palettes with "direction"
display.ghibli(direction="random")
```
### Integration with ggplot2
**Add discrete palette to ggplot:**
```
plot.colorblind.ghib("Totoro-Mouth")
```
**Add continuous palette to ggplot:**
```
plot.colorblind.ghib("Totoro-Mouth")
```



# Colorblind-friendly palette assistance
We carefully created and tested colorblind-friendly palettes in our package. In addition, we also added the option for the user to study themself which colors in a palette are more problematic in regard to colorblind-friendliness. It is important to note that while some palettes aren't labeled as "colorblind-friendly," removing one or two colors can help achieve that. Our function to visualize palettes and check if they are clolorblind-friendly also work with any palette defined by the user.

**Display all colorblind-friendly palettes:**
```
display.ghibli(colorblind_only = T)
```
![all-cb](https://github.com/goboru/GhibliBrewer/assets/102520815/0d2515cc-c2e5-4087-bbe9-88142d73c390)

**Simulate a GhibliBrewer palette in the way that a person with protanopia, deuteranopia, or tritanopia would see them, respectively:**
```
plot.colorblind.ghib("Totoro-Mouth")
```

**Simulate any palette in the way that a person with protanopia, deuteranopia, or tritanopia would see them, respectively:**
```
palette <- c('red', 'green', 'orange', 'black')
plot.colorblind.palette(palette)
```

### Editing a palette considering colorblindness
A good example of a palette that is close to being colorblind-friendly is "Howl-Peace". We can visualize this palette using plot.colorblind.ghib()
```
plot.colorblind.ghib("Howl-Peace")
```
![colorblind-example](https://github.com/goboru/GhibliBrewer/assets/102520815/e19e4415-00b8-4e08-b907-0734e8c92592)

You can notice that the most problematic combination in this palette is between colors 2-7(tritanopia) and 4-7(deuteranopia and protanopia). We can remove one of them (#7), and, even if intuitively this palette does not appear colorblind-friendly, you can see that there is no highly-problematic combination now:
```
palette <- ghibli.brewer("Howl-Peace")[c(1,2,3,4,5,6)]
plot.colorblind.palette(palette)
```
![colorblind-fixed](https://github.com/goboru/GhibliBrewer/assets/102520815/918960eb-77b4-41b9-9e28-f8b33e37775a)


# GhibliBrewer palettes

## All palettes
![All](https://github.com/goboru/GhibliBrewer/assets/102520815/f1b88ae4-4384-4168-b3cb-e91d49c3426e)


## Nausicaä of the Valley of the Wind (1984)
### Nausicaa-Pilot


### Nausicaa-Bug


## Castle in the Sky (1986)
### Sky-Grass


### Sky-Necklace


## My neighbour Totoro (1988)
### Totoro-Umbrella


### Totoro-Mouth


### Totoro-Catbus

### Totoro-House

### Totoro-School


## Only Yesterday (1991)
### Yesterday-Park


## Porco Rosso (1992) 
### Porco-Plane

### Porco-Cave

## Pom Poko (1994)
### Pompoko-Fortune

## On Your Mark (1995)
### Mark-Car


## Princess Mononoke (1997)
### Mononoke-Hug

### Mononoke-Knife

### Mononoke-Guardian

## My Neighbors the Yamadas (1999)
### Yamadas


## Spirited away (2001)
### Chihiro-Dragon

### Chihiro-Lump

### Chihiro-Bridge

### Chihiro-NoFace


## The Cat Returns (2002)
### Cat-Vals

### Cat-Prince

### Cat-Broom

### Cat-Bubble


## Howl's Moving Castle (2004)
### Howl-Horizon

### Howl-Peace

### Howl-Terrace

### Howl-FireDemon

### Howl-Star

### Howl-Breakfast

### Howl-Castle


## Tales from Earthsea (2006)
### Earthsea-Silk

### Earthsea-Lightning


## Arrietty (2010)
### Arrietty-Garden

### Arrietty-Bedroom


## Ponyo (2008)
### Ponyo-Joy

### Ponyo-Ramen

### Ponyo-Boat


## The Wind Rises (2013)
### Wind-Timer

### Wind-Kiss

## When Marnie Was There (2014)
### Marnie-Bedroom

### Marnie-Train


## The Boy and the Heron (2023)
### Heron-Troop

### Heron-Jelly

### Heron-Parrots

### Heron-Hug




*If you have come this far, why don't you try your expertise with game.ghib() ?*
