# Data Catalog Entry Form (DCEF)

Before a researcher goes out into the field (and after returning), they are required to fill out a data catalog entry form (DCEF).

The data catalog entry form includes important infomration about the who, what, where, and when of the data a researcher collects on their field trip.
The DCEF is saved in a `.yml` format so we can build up a larger relational database of projects and data collected over time-- the data catalog.
With this we can do bookkepping for who was invloved in what projects, and what grants paid for them., and extract data associate with particular species or locations over time.
An initial `.yml` can be created and modified each subsequent field trip. The bulk of the work is in the first upload and you will want this info for your data management plan, project readme, and future publications.

The DCEF gets attached to each "data cata log entry" or "data chunk" zip file or tarball which will be sent to Garching and recorded on tape to preseve it. These data catalog entries are collated by Andreas whi links the unique of each tarball into the DCEF once they create them.

The DCEF is also of use for the researcher to see what grants funded their projects, and to give credit to others if the data is used in a future project decades down the line for coauthorship, consulation, etc.

# How do I access the Data Catalog Entry Form

It can be accessed at this website: https://bjbarrett.shinyapps.io/data_catalog_entry_form_shiny_yml/

It can also be accessed by running the `create_yml.R` code in this repository.

The data catalog entry form will be automatically named after the `data_catalog_entry_id` you provide and is appended with `yyyymmdd_hhmmss` of creation e.g:
`coiba_capuchins_july_2021_20211019_123741.yml`

# What goes into the data catalog entry form

## 1. `data_catalog_entry_id`
This is unique identifier for the entry you data catalog entry you want to archive.
For example one could use `coiba_capuchins_july_2021` or `kob_apple_data_2021`.

## 2. `data_catalog_entry_details`
    This is particular info about the entry. Namely:
    1. `project_name`: This is the name of your server folder if it is a long term project. It is a drop down menu which needs to get updated as projects are added.
    2. `server_adress`: location on server where data catalog entry is stored

## 3. `person`
People involved in project. Make an an entry for each person.
    1. `name` is researcher name
    2. `institute` is institutional affiliation(s)
    3. `email`
    4. `role`: What is role in project (dropdown menu)
    5. `uploader`: Yes or No if they are responsible for data catalog entry upload *default is no*

## 4. `species`
    Info about target species (1 or more)
    1. `name_eng`  is common name in english
    2. `name_loc` is local name at fieldsite (i.e. mono cariblanco)
    3.  `name_sci` is Linnean Genus species

## 5. `dates`
    Select a range of dates where data will be/was collected.

## 6. `location`
    Info about location(s) of data collection.
    1. `country` choose from drop down
    2. `region`: if applicable
    3. `city`: nearest city if applicable
    4. `park`: name of park or protected area if applicable
    5. `field_station`: name of field station i.e. BCI or Mpala or KOB if applicable
    6. `lat_log`: Latitude (e.g. 9.167) and Longitude (e.g. 47.679) in Decimal Degrees

## 7. `data_type_overview`
    Type(s) of data that will be collected such as behavioral, movement, ecological, tissue samples.
     Select from a drop down menu, and let us know if you want to make another (or fork and modify changes and ask to merge)

## 8. `data_description`
    A brief free form text entry describing the data and general goals of project. Can be lifeted from your Data Management Plan.

## 9. `funding_sources`
    A list of all grants numbers, agencies, and istituons that funded this field work.

## 10. `keywords`

Relevant Keywords that you think describe your project

# How to create a data catalog entry form
## Accessing the form
### Website
[Click this, bitte!](https://bjbarrett.shinyapps.io/data_catalog_entry_form_shiny_yml/)
### Locally as ShinyApp in RStudio
To run this you will need to open the file `create_yml.R` with [RStudio](https://www.rstudio.com/) and search for the *Run App* button:

![](img/run_app.svg)

This repo uses the {[renv](https://rstudio.github.io/renv/articles/renv.html)} package.
 So If you want to make sure to use the same setup that was used for the creation of the app, please start RStudio with `create_project_yml.Rproj` and call `renv::restore()` from that R session.
 (You might need to install {renv} first with `install.packages("renv")`)

## Create or Modify a File

After this, a window should pop up that allows you to load an existing `yml` file or to create a new one from scratch.

### Creating a new File from scratch

![](img/new_yml.png)

### Loading and Modifying an Existing File
Loading an existing file (eg. the provided demo `starwars.yml` or a previous data catalog entry form you created and want to update.

![](img/load_yml.png)

The created/modified `yml` file can be save using the *Download* button within the *modify* tab.


# Is there an example or template?
[Click here to see a template](https://github.com/livingingroups/data_catalog_entry_form_shiny_yml/blob/master/coiba_capuchins_july_2021_20211019_123741.yml)
