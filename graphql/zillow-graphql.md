# Zillow GraphQL Schema

## Overview

This is a conceptual GraphQL schema for the Zillow real estate search and data platform. Zillow is the largest U.S. real-estate marketplace, offering home and rental listings, Zestimate home value estimates, mortgage tools, and a connected agent and lender ecosystem.

Programmatic access to Zillow Group listing, broker, and lender data is delivered through Bridge Interactive (bridgedataoutput.com) for licensed real-estate professionals and MLSs, the Zillow Tech Connect partner program for vendors, Mortech for mortgage pricing, and the Showcase listing enhancement product.

This GraphQL schema is a conceptual representation based on the publicly documented data surfaces from Bridge Interactive (RESO Web API / OData), Zillow Tech Connect, Mortech, and Zillow Showcase.

## Schema Source

- Bridge Interactive API: https://bridgedataoutput.com/docs/platform/
- Zillow Tech Connect: https://www.zillowgroup.com/tech-connect/
- Mortech API: https://www.mortech-inc.com
- Zillow Showcase: https://www.zillow.com/z/showcase/

## Core Domains

### Property and Listings

The schema models real estate properties as `Property` objects with nested `Address`, `GeoLocation`, `Coordinates`, and `ZestimateValue` types. Full listing detail is expressed through `PropertyListing` and `ListingDetail`, with MLS-specific data captured in `MLSListing`.

### Valuation

`ZestimateValue`, `HomeEstimate`, and `HomeWorth` represent Zillow's automated valuation models. Historical valuation and tax data are modeled through `PriceHistory`, `PriceEvent`, `TaxHistory`, and `TaxRecord`.

### Location and Neighborhood

Geographic context is provided through `Neighborhood`, `NeighborhoodBoundary`, `School`, and `SchoolRating`. Livability scores are captured through `WalkScore`, `TransitScore`, and `BikeScore`. Risk data surfaces through `FloodRisk` and `FireRisk`.

### Media

Immersive listing media is represented by `Zillow3D`, `VirtualTour`, `FloorPlan`, and `Photo`. These align with the Zillow Showcase product which provides interactive floor plans and AI-enhanced photography.

### Agents and Brokerages

The agent and brokerage ecosystem is modeled through `ListingAgent`, `AgentProfile`, `BrokerageListing`, `Brokerage`, and `AgentSearch`. The Zillow Tech Connect partner program surfaces lead and contact workflows through these types.

### Transactions

Buyer and seller workflows are captured through `OpenHouse`, `ShowingRequest`, `ForSaleByOwner`, `NewConstruction`, `HomeBuilder`, and `Community`.

### Mortgage

Mortech's pricing engine is represented by `MortgageEstimate`, `MonthlyPayment`, `DownPayment`, and `AffordabilityCalc`.

### Search and Saved State

Search workflows are modeled through `SearchFilter`, `SearchResult`, `SavedHome`, and `SavedSearch`. Rental-specific types include `RentalListing`, `RentalAmenity`, and `PetPolicy`.

### Map

Geographic display context is represented by `ZillowMap`.

## Types Count

This schema defines 53 named GraphQL types covering properties, listings, valuations, neighborhoods, agents, brokerages, mortgage estimates, media, and search workflows.

## Usage Notes

This is a conceptual schema. Actual programmatic access to Zillow Group data requires:

1. MLS approval via Bridge Interactive for listing and broker data
2. Zillow Tech Connect partner vetting for CRM and lead integration
3. Mortech licensing for mortgage pricing data
4. Zillow Showcase MLS feed agreements for immersive media

Contact Zillow Group at https://www.zillowgroup.com/developers for partner onboarding.
