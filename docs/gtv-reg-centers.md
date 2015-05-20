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

#### 1.3. Data Loading

##### 1.3.1. Structure the Data

Make sure that the data is the following column order and format:

- `Id`
  - Type: number
  - Description: Unique identifier of each row of data.
- `Region_Code`:
  - Type: number
  - Description: Unique identifier per region. This is the top most administrative boundary level.
- `Region_Name`:
  - Type: text
  - Description: Matched to the region code.
- `District_Code`:
  - Typer: number
  - Description: Unique identifier per district. Administrative boundary level after the region. Region is bigger and could have many districts.
- `District_Name`:
  - Type:text
  - Description: Relating to district code.
- `Electoral_Code`:
  - Type: number
  - Description: Unique identifier per electoral administrative boundary level after district. Electoral area is smaller than a district. Many electoral areas make a district.
- `Electoral_Name`:
  - Type: number
  - Description: Electoral area name relating to the electoral code.
- `Reg_Centre_Code`:
  - Type: number
  - Description: Unique identifier for each registration centre.
- `Reg_Centre_Name`:
  - Type: text
  - Description: Registration centre name
- `Other_Polling_Stations` (Optional):
  - Type: text
  - Description: Most registration centres happen to be polling stations but not all polling station are registration centres. This column can be added to create more polling stations.

*Sample of the above data structure can be found [here](https://www.google.com/fusiontables/DataSource?docid=1NMs_iAwYIZqdEBDVVuxA7nN4BQlvQwNAgevtPkYx#rows:id=1).*

You can use whatever tools you wish to use for the structuring of data, and we recommend using either [Google Sheets](https://www.google.com/sheets/about/) or [Open Refine](http://openrefine.org/), or a combination of both. MS Excel is fine too.

**Once done, export the data in CSV or TSV format.**

##### 1.3.2. Import into Fusion Tables

The data for GotToVote! Registration Centres lives on Fusion Tables. If you're not familiar with Google Fusion Tables, try the [Tutorials](http://www.google.com/support/fusiontables/bin/answer.py?answer=184641).

Create a new fusion table and Import the CSV (or TSV) from your computer.

##### 1.3.3. Access Data via Fusion Tables API

The [Fusion Tables REST API](https://developers.google.com/fusiontables/docs/v2/getting_started) provides an easy way to query our table without having to load the entire dataset.

For GotToVote! Registration Centres, we need two things:

1. Google API Key [[Steps](https://developers.google.com/fusiontables/docs/v2/using#APIKey)]
2. Table ID [[Reference](https://developers.google.com/fusiontables/docs/v2/getting_started#background-concepts)]

Follow the getting started guide [here](https://developers.google.com/fusiontables/docs/v2/getting_started) for more information.

Once done, edit the `js/main.js` file as follows:

    ...
    var api_key = "&key=YOUR_API_KEY";
    
    county_sel.onchange = function () {
      ...
      } else {
        ...
        run_get_centres("YOUR_TABLE_ID");
      }

So that the data is accessible, make sure the [table access permissions](https://developers.google.com/fusiontables/docs/v2/using#authTbl) is not *Private*.

#### 1.4. Deployment

Now you're ready to rumble. If you would like to see the platform in action on your local machine, simply open the folder in terminal or command prompt and run `jekyll serve`. You should then be able to see your version of GotToVote! Registration Centres on http://localhost:4000/

To deploy using Github Pages, just commit and push your latest changes and the platform should be available at http://[YOUR_USERNAME].github.io/GotToVote.Ghana/

To use a custom URL e.g mycountry2015.org follow the steps [here](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/).

***We are also very much willing to make mycountry.gottovote.cc available to you so please reach out to [hello[at]gottovote[dot]cc](mailto:hello@gottovote.cc).***

---

#### Contact

Any questions on setting up GotToVote? Get in touch at [support[at]gottovote[dot]cc](mailto:support@gottovote.cc) 


