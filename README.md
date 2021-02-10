<p align="center">
  <a href="https://www.gatsbyjs.com/?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter">
    <img alt="Gatsby" src="https://www.gatsbyjs.com/Gatsby-Monogram.svg" width="60" />
  </a>
</p>
<h1 align="center">
  Gatsby minimal instant-meilisearch starter
</h1>

## 🚀 Quick start

1.  **Create a Gatsby site.**

    Use the Gatsby CLI to create a new site, specifying the minimal starter.

    ```shell
    # create a new Gatsby site using the minimal starter
    npm init gatsby
    ```

3.  **Add instant-meilisearch dependencies.**

    ```shell
    # create a new Gatsby site using the minimal starter
    yarn add react-instantsearch-dom @meilisearch/instant-meilisearch instantsearch.css
    ```

2.  **Add Instant MeiliSearch to your application.**

    Open `src/pages/index.js`, and replace all the code with the following:

    ```javascript
    import React from 'react';
    import { InstantSearch, SearchBox, Hits, Highlight } from 'react-instantsearch-dom';
    import instantMeiliSearch from '@meilisearch/instant-meilisearch';

    const searchClient = instantMeiliSearch(
      "https://demos.meilisearch.com",
      "dc3fedaf922de8937fdea01f0a7d59557f1fd31832cb8440ce94231cfdde7f25"
    );

    const Hit = ({ hit }) => (
      <div>
          <h4>
            <Highlight attribute="name" hit={hit} tagName="mark" />
          </h4>
      </div>
    )

    const IndexPage = () => (
      <InstantSearch
        indexName="steam-video-games"
        searchClient={searchClient}
      >
        <SearchBox />
        <Hits hitComponent={Hit} />
      </InstantSearch>
    );

    export default IndexPage
    ```

3.  **Start developing**

    Navigate into your new site’s directory and start it up.

    ```shell
    cd my-gatsby-site/
    npm run develop
    ```

4.  **Open the code and start customizing!**

    Your site is now running at http://localhost:8000!

    Edit `src/pages/index.js` to see your site update in real-time!

## Go Further

If you run this repo we made an example with more UI elements.