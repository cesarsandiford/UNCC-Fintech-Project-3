# Art Registry Through NFT Marketplace

Creation of a dApp for the artwork registry contract and appraisals.

### 1. Deploy the Contract

1. In the Remix IDE, `ArtRegistry.sol` smart contract was selected.

2. Launched a Quickstart blockchain with Ganache, and then used the private key of a wallet to import it to MetaMask and used the Remix IDE to compiled and deployed the `ArtRegistry` contract.


### 2. Prepare the Environment File

In the .env file, `WEB3_PROVIDER_URI` has the value of the RPC Server field in Ganache. 
For the `SMART_CONTRACT_ADDRESS` value, I used the address of the deployed contract in the Remix IDE. You can find it in the Deployed Contracts section.



### 3. Build the dApp

1. Open `app.py`.

2. In `app.py`, in the “Register New Artwork” section:

    * Used Lottie Animation with the function: `def load_lottieurl(url: str)`:
    
    * Have a url to pull from: `lottie_marketplace = load_lottieurl`

    * Defined new Streamlit components to get the following data from the user:

        * The name of the artwork

        * The name of the artist

        * The initial appraisal value

        * The URI of the artwork

    * Created a button named “Register Artwork” that uses the contract's `registerArtwork` function to register the data that you get from the Streamlit components.

    * Display the transaction receipt on the webpage.

3. In `app.py`, in the “Appraise Art” section:

    * Use Web3.py to call the `newAppraisal` function of the contract to record a new appraisal when someone clicks the Appraise Artwork button. Use the first account, in `w3.eth.accounts[0]` for the transaction.

4. In `app.py`, in the “Get Appraisals” section:

    * Create a Streamlit component that gets an artwork token ID from the user.

    * In the button code, create a filter that lists all the appraisal events for the token.

    * Display all the entries from the event filter on the webpage.

5. Run the application by using `streamlit run app.py`. Test the functionality of the dApp to make sure that it works as expected.

## Created by: Cesar Sandiford

## References:

Module 22.2.4 Appraising the Situation

https://lottiefiles.com/

https://www.youtube.com/watch?v=TXSOitGoINE

https://github.com/andfanilo/streamlit-lottie

