### 1. GotToVote! Registration Centres

The first of the GotToVote! components to be built. This allows easy display and finding of registration centers.

**Demo:** [http://ghana.gottovote.cc](http://ghana.gottovote.cc)

#### 1.1. Requirements

GotToVote! Registration Centres uses:

1. [Github Pages](https://pages.github.com/) - Serve the HTML
2. [Fusion Tables](https://developers.google.com/fusiontables/) - Store the database of registration centres

As such, you would need Github and Google accounts respectively. Both are free.

To test the webserver on your own machine, you will need to install [Jekyll](http://jekyllrb.com/).


#### 1.2. Installation

Start by [creating a fork](https://help.github.com/articles/fork-a-repo/) of [GotToVote! Ghana repository](https://github.com/CodeForAfrica/GotToVote.Ghana).

Once done you can clone your version onto your local machine.

    git clone https://github.com/[username]/GotToVote.Ghana.git

To see it in action almost immediately run:

    cd GotToVote.Ghana
    jekyll serve

That's it. If you visit [http://localhost:4000/](http://localhost:4000/) you'll see a vanilla version of GotToVote! Ghana.

#### 1.3 Data Loading

##### 1.3.1 Structure the Data

Make sure that the data is the following column order and format:

- `Id`
  - Type: number
  - Description: Unique identifier of each row of data.
- `Region_Code`:
  - Type: number
  - Description: Unique identifier for each region. This is the top most administrative boundary level.
- `Region_Name`:
  - Type: text
  - Description: Matched to the region code.
- `District_Code`:
  - Typer: number
  - Description: Unique identifier for each district. Administrative boundary level after the region. Region is bigger and could have many districts.
- `District_Name`:
  - Type:text
  - Description: Relating to district code.
- `Electoral_Code`:
  - Type: number
  - Description: 
- `Electoral_Name`:
  - Type: number
  - Description: 
- `Reg_Centre_Code`:
  - Type: number
  - Description: 
- `Reg_Centre_Name`:
  - Type: text
  - Description: 
- `Other_Polling_Stations` (Optional):
  - Type: text
  - Description: 

*Sample of the above data structure can be found [here](https://www.google.com/fusiontables/DataSource?docid=1NMs_iAwYIZqdEBDVVuxA7nN4BQlvQwNAgevtPkYx#rows:id=1).*

You can use whatever tools you wish to use for the structuring of data, and we recommend using either [Google Sheets](https://www.google.com/sheets/about/) or [Open Refine](http://openrefine.org/), or a combination of both. MS Excel is fine too.

**Once done, export the data in CSV or TSV format.**

##### 1.3.2 Import into Fusion Tables

The data for GotToVote! Registration Centres lives on Fusion Tables. If you're not familiar with Google Fusion Tables, try the [Tutorials](http://www.google.com/support/fusiontables/bin/answer.py?answer=184641).

Create a new fusion table and Import the CSV (or TSV) from your computer.

##### 1.3.3 Access Data via Fusion Tables API

The Fusion Tables REST API provides an easy way to query our table without having to load the entire dataset.




