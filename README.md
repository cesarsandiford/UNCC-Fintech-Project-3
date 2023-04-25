# Art Registry Through NFT Marketplace

Creation of a dApp for the artwork registry contract and appraisals.

### 1. Deploy the Contract

1. In the Remix IDE, `ArtRegistry.sol` smart contract was selected.

2. Launched a Quickstart blockchain with Ganache, and then used the private key of a wallet to import it to MetaMask and used the Remix IDE to compiled and deployed the `ArtRegistry` contract.

<img width="412" alt="Screenshot 2023-04-24 at 8 37 29 PM" src="https://user-images.githubusercontent.com/112976523/234147805-a97cde14-d2f7-46fe-92c9-c57f3d59439d.png">



<img width="845" alt="Screenshot 2023-04-24 at 8 38 02 PM" src="https://user-images.githubusercontent.com/112976523/234147772-220177b1-80d7-4d39-9077-f8fa0a62e3dd.png">


### 2. Prepare the Environment File

In the .env file, `WEB3_PROVIDER_URI` has the value of the RPC Server field in Ganache. 
For the `SMART_CONTRACT_ADDRESS` value, I used the address of the deployed contract in the Remix IDE. You can find it in the Deployed Contracts section.

<img width="713" alt="Screenshot 2023-04-24 at 8 45 27 PM" src="https://user-images.githubusercontent.com/112976523/234147957-239d04dc-9605-4735-838d-c207f97eed98.png">


### 3. Build the dApp

1. Open `app.py`.

2. In `app.py`, in the “Register New Artwork” section:

     Used Lottie Animation with the function: `def load_lottieurl(url: str)`:
    
     Have a url to pull from: `lottie_marketplace = load_lottieurl`

     Defined new Streamlit components to get the following data from the user:

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

5. Run the application by using `streamlit run app.py`.
    
    <img width="1190" alt="Screenshot 2023-04-24 at 8 49 12 PM" src="https://user-images.githubusercontent.com/112976523/234148316-959ba099-7904-44c8-963f-17201568a416.png">

    
    * Test functionality by typing relevant information in order to register your artwork and do an appraisal.

## And the Artwork is successfully registered and appraised.

<img width="670" alt="Screenshot 2023-04-24 at 8 41 47 PM" src="https://user-images.githubusercontent.com/112976523/234148092-66973ca3-1e6e-48d8-9a64-ae2887bd7bd1.png">


<img width="651" alt="Screenshot 2023-04-24 at 8 42 10 PM" src="https://user-images.githubusercontent.com/112976523/234148018-8f2c8fbc-eef2-413b-8dec-f161d19c73e9.png">

<img width="659" alt="Screenshot 2023-04-24 at 8 42 19 PM" src="https://user-images.githubusercontent.com/112976523/234148047-f76e2734-ebd5-4b2d-aff9-2554cf4b66db.png">



## Created by: 

Cesar Sandiford

## References:

* Module 22.2.4 Appraising the Situation

* https://lottiefiles.com/

* https://www.youtube.com/watch?v=TXSOitGoINE

* https://github.com/andfanilo/streamlit-lottie

