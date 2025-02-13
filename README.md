# joule-functions-example

In this repository, you will find a reference for an assistant built with the Joule Functions approach.
We will explain how to define a scenario using an LLM-based dialog management and response generation.

For instructions on all three examples please check the corresponding tutorials below.
If you want to adapt or build content on your own, consider the [Content Building Guideline](https://sap.sharepoint.com/:b:/r/teams/JouleFunctionsPilot/Shared%20Documents/General/Content_Building_Guideline_Joule_Functions.pdf?csf=1&web=1&e=OirLGA).

**Disclaimer:** Joule Functions are supported with spec version `3.x.x` and will not be made available on staging landscape, as it's not a productive landscape and planned to be decommissioned. Please use internal prod landscape instead, which is now available on BTP Canary `eu12` - so you can subscribe it in the same subaccount you're already using for staging and then remove the staging subscription. The required entitlements are showing up as `das-application-canary` and `das-service-canary` in SAP BTP Control Center. If you are unsure on which landscape, type the command `joule status` and check the API url.

## Content

```
└── capabilities/ // assistant root
    ├── da.sapdas.yaml  // assistant definition combining capabilities
    ├── helloworld/ // a very simple hello world capability
    ├── weather/ // a capability calling an external API
    └── products/ // a more comeplex example showing products from an OData service
    
```

> A more complex example for the flight search can be found in a dedicated [branch](https://github.tools.sap/DAS-Samples/joule-functions-example/tree/fb_flight_search).

## Joule Functions Tutorials

You can choose between three different hands on tutorials:

* [Hello World - Basic setup and defining a very simple hello world capability](tutorials/helloworld/index.md)
* [Fetch Weather - Joule function calling an external API](tutorials/weather/index.md)
* [Search Products - A more complex example showing products from an OData service](tutorials/products/index.md)

## All-in-one example

1. Clone this repository to your local workspace.
1. Go to the folder `capabilities` and run `joule login` to log in to your subaccount.
2. Run `joule deploy -c -n <assistant_name>` to compile and deploy the assistant to your subaccount.
3. Run `joule launch <assistant_name>` to test the assistant with all three capabilities.

*Hint:* You must set up the corresponding destinations in your BTP account to make the capabilites `weather` and `products` work. Check the corresponding tutorials to see how.

## Testing

Please be aware that the current implementation of the Cucumber/Gherkin test
framework is not yet fully working with the generated LLM responses in the new Joule architecture.
Support for this is planned for the future, therefore we skip explaining tests here in these tutorials.

If you are interested in the topic, check the existing [hands on material](https://github.tools.sap/DAS-Samples/da-mc-developers-hands-on/tree/8-Adding-Content-Tests).

## Related Information

[SAP Help - Joule Development](https://help.sap.com/docs/joule/service-guide/development?locale=en-US)
