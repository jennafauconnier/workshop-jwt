# JWT Workshop

The goal of this workshop is to demonstrate the vulnerability of a weak JWT secret key.


Once cloned, go to the root of the repo and run the `npm install` command to install the dependencies.

Once in the repo, run the `npm run gen-candidate-keys` command.

A new candidateKeys file has been created, containing all possible combinations of 4 lower-case letters.

You can change the key generation criteria by modifying the `candidateKeysGenerator.ts` file if you wish.

Run the `npm run gen-jwt` command to generate a JWT token yourself. Look at the `jwt` file that has been created. It consists of the header, payload and signature, encoded in base 64 and separated by dots.


Now that you've generated a JWT and a list of potential keys, you're going to try and find the key that was used to generate the JWT. To do this, retrieve the header and payload of the generated JWT and generate a signature for each key in the list.

It will repeat this process until the signature generated matches the signature of the JWT, at which point you will have found the key used to generate the JWT and you will be able to generate JWTs yourself that will be validated by the server.

Look at the code in the `crack.ts` file and then use it by running the `npm run crack` command.

You will see in the console all the attempts until the secret has been recovered.

