




nombre <- "Mayli"

saludo <- "Hola"



paste(saludo, nombre)


x <- c(12,15,17,20)

mean(x) #Media de la variable x

mean(X) #Esto indica error
#Instalar y llamar librerias
#Install packages
library(inti)
library(dplyr)
library(huito)
# 1. Define factors: Bean genotypes and fertilization doses
factors_rcbd <- list(
  Fertilization = c("0", "50", "100")
)

# 2. Generate RCBD layout
rcbd_exp <- design_repblock(
  nfactors = 1,
  factors = factors_rcbd,
  type = "rcbd",
  rep = 4,
  serie = 10,
  zigzag = TRUE,
  seed = 2026
)

fb <-rcbd_exp$fieldbook

# Field layout visualization
tarpuy_plotdesign(
  data = rcbd_exp,
  factor = "Fertilization",
  fill = c("plots", "ntreat")
)
#Etiquetas
font <- c("Permanent Marker", "Tillana", "Courgette")

huito_fonts(font)

label <- fb %>%  
  label_layout(size = c(10, 2.5)
               , border_color = "blue"
  ) %>%
  include_image(
    value = "https://flavjack.github.io/inti/img/inkaverse.png"
    , size = c(2.1, 2.4)
    , position = c(1.2, 1.25)
    # , opts = list("image_scale(200)", "image_noise()")
  ) %>%
  include_barcode(
    value = "barcode"
    , size = c(2.5, 2.5)
    , position = c(8.2, 1.25)
  ) %>%
  include_text(value = "INKAVERSE"
               , position = c(4.6, 2)
               , size = 20
               , font = font[1]
               , fontface = "bold"
               , color = "red"
  ) %>%
  include_text(value = "Fertilization"
               , position = c(2.7, 1.2)
               , size = 12
               , font = font[2]
               , opts = list(hjust = 0.0, vjust = 0.0) 
               , color = "black"
               , prefix = "Fertilization: "
               , fontface = "bold"
  ) %>%
  include_text(value = "ntreat"
               , position = c(4.5, 0.5)
               , size = 12
               , color = "#009966"
               , font = font[2]
               , prefix = "Ntreat: "
               , fontface = "bold"
  ) %>% 
  include_text(value = "plots"
               , position = c(9.7, 1.25)
               , angle = 90
               , size = 12
               , color = "brown"
               , font = font[3]
               , prefix = "Plot: "
  ) 

label %>% label_print(mode = "preview")
