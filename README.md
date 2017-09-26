# block_certs_codex

## Intent

This guide is a work in progress and should not be considered a completed guide, however, the goal of this document is to be a complete guide to creating, issuing and viewing Blockcert certificates. As the Blockcerts technology changes so will, hopefully, this guide.

## Guide start

First clone the cert-tools package from [here](https://github.com/blockchain-certificates/cert-tools). 

A few things are going to occur in this package, first we're going to modify some settings to create a custom template, then we're going to use that template in conjunction with our roster.csv file to generate some unsigned certificates which we will send to our cert-issuer.

Follow the installation procedure outlined in the readme of the link from above.

## Overview

> See sample_data for example configuration and output. conf-mainnet.ini was used to create a batch of 2 unsigned certificates on the Bitcoin blockchain.

> The steps were:

> Create the template
> Update the config file to contain the correct data to populate the certificates
> Place the needed images in images/ and point to them in the config file
> Run create_certificate_template.py, which resulted in the certificate template /certificate_templates/test.json
> Instantiate the batch
> Add the recipient roster (in this case rosters/roster_testnet.csv) with the recipient's Bitcoin addresses.
> Run 'instantiate_certificate_batch.py', which resulted in the files in unsigned_certificates
> Then the unsigned certificates were copied to cert-issuer for signing and issuing on the blockchain.

## Changing Images

To change the logo image and the signature image you will need to add the image files to the images folder inside sample_data and then make some adjustments to the conf.ini file. Look for the #images tag and there you can replace the default images file names with the names of the files you just uploaded. 

## Changing the text on the certificate.

When a user goes to view the certificate they are going to see text from the certificate as well as some text that is generated by the cert-viewer. The issuer and certificate information fields can be replaced with custom data on the conf.ini while some of the other text and images should be changed in the cert-viewer code.

The issuer_public_key=ecdsa-koblitz-pubkey: is generated from the bitcoin wallte you use when we switch from "regtest" to "testnet" or "mainnet" coins. For now, just use the defualt values.

## Changing 

## Adding a Custom field





