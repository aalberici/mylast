# Business Requirements Document
# Porrettana Gomme MDM Integration with Evolutivo

## 1. Executive Summary

Porrettana Gomme Spa requires integration between their existing management system and the Evolutivo platform to create a comprehensive Master Data Management (MDM) solution focused on product catalog management and pricing optimization. This integration aims to improve data quality, streamline pricing strategies, and provide actionable business intelligence for commercial decisions. The solution will create a centralized data hub that aggregates information from multiple sources, standardizes it, and enables effective business analytics.

## 2. Project Overview

### 2.1 Background

Porrettana Gomme Spa operates in the tire retail business with multiple locations (Bologna, Pistoia, Silla) and needs to optimize its product catalog management and pricing strategy. The current system faces challenges with obsolete product references, complex pricing updates, and limited ability to analyze sales data strategically. The company relies on PreCat data from manufacturers for most products, but also needs to manage non-PreCat products obtained through Excel sheets from distributors.

### 2.2 Business Objectives

- Create a centralized product catalog that eliminates obsolete references
- Implement a flexible and dynamic pricing system
- Enable cross-referencing and identification of equivalent products
- Generate business intelligence for strategic pricing and stock decisions
- Streamline and automate the price update process
- Improve data consistency across all locations
- Prepare for future omnichannel strategy including B2B e-commerce

### 2.3 Stakeholders

- Marco Gandolfi (Porrettana Gomme) - Primary business stakeholder
- Andrea Alberici (Evolutivo) - Platform specialist
- Davide Castioni (Evolutivo) - Technical specialist
- ngbit - Technology partner responsible for security

## 3. Detailed Requirements

### 3.1 Data Integration Requirements

#### 3.1.1 Data Sources Integration
- Connect to Porrettana Gomme's management system through secure API/file exchange
- Create data mappings for real-time or scheduled data extraction
- Support importing PreCat data from tire manufacturers
- Support importing non-PreCat data via Excel files
- Implement processes for data quality control and standardization

#### 3.1.2 Master Data Management
- Establish a central product repository with de-duplication capabilities
- Implement product equivalence mapping to identify substitutable products
- Track product lifecycle status (active, obsolete, etc.)
- Manage complex product attributes specific to tires (size, season, speed index, etc.)
- Support location-specific inventory visibility

### 3.2 Pricing Management Requirements

#### 3.2.1 Price Calculation
- Support complex pricing formulas based on purchase cost
- Enable differential pricing based on product attributes (vehicle type, manufacturer)
- Support time-limited promotional pricing
- Maintain history of pricing changes
- Track purchase prices by order/batch for margin analysis

#### 3.2.2 Price List Generation
- Generate and update "Listino 90" as the primary price list
- Support scheduled or on-demand price updates
- Enable mass price updates based on criteria (e.g., all tires size 18" and larger)
- Track price validity periods
- Support flexible margin rules based on product category, brand, and other attributes

### 3.3 Business Intelligence Requirements

#### 3.3.1 Analytics Dashboard
- Provide sales analysis by product, category, and location
- Track margin performance across product lines
- Analyze inventory levels and movement
- Support cross-referencing of similar products for strategic pricing

#### 3.3.2 Reporting
- Generate standard reports for sales, inventory, and pricing
- Support ad-hoc query capabilities
- Enable export to Excel for further analysis
- Track KPIs related to catalog size, obsolete products, and pricing effectiveness

### 3.4 Security Requirements
- Implement secure data exchange between systems
- Provide role-based access controls
- Ensure firewall configurations allow secure data transfer
- Maintain audit logs of system access and changes
- Ensure all data transfers comply with data protection regulations

## 4. Technical Requirements

### 4.1 Integration Architecture

#### 4.1.1 System Components
- Evolutivo platform as the central MDM system
- Porrettana Gomme's management system as the operational system
- Integration layer for data synchronization
- Analytics module for business intelligence

#### 4.1.2 Data Flow
- Bidirectional synchronization of product data
- One-way transfer of sales data for analysis
- Real-time or scheduled data exchange based on business needs
- XML/flat file format for data exchange

### 4.2 Technology Stack
- Evolutivo platform (Business Process Management)
- SQL Server database access (read-only view)
- Web services for real-time integration
- Business Rules Engine for pricing logic
- Dashboard tools for analytics

### 4.3 Performance Requirements
- Support catalog of 10,000+ product references
- Price updates processing within acceptable timeframes (ideally under 1 hour)
- Analytics queries response time under 10 seconds
- System availability during business hours with minimal downtime

## 5. Implementation Approach

### 5.1 Phased Implementation
1. **Phase 1:** Data Integration and Base MDM Implementation
   - Connect systems and establish data flow
   - Implement product catalog with de-duplication
   - Set up basic pricing management

2. **Phase 2:** Enhanced Pricing and Analytics
   - Implement complex pricing rules
   - Develop analytics dashboard
   - Enable dynamic price updates

3. **Phase 3:** Advanced Features (Future)
   - B2B e-commerce integration
   - Customer segmentation pricing
   - Predictive analytics for pricing optimization

### 5.2 Timeline
- Project Kickoff: Immediate
- Phase 1 Completion: Within 1-1.5 months (before seasonal peak)
- Phase 2 Completion: 2-3 months after Phase 1
- Phase 3: To be determined based on business priorities

### 5.3 Resources
- Evolutivo development team
- Porrettana Gomme IT support and business users
- ngbit security team for firewall and security configuration

## 6. Success Criteria

### 6.1 Business Success Metrics
- Elimination of obsolete product references in active catalog
- Reduction in time spent on price updates by at least 75%
- Improved margin visibility across product lines
- Increased pricing flexibility and responsiveness to market conditions
- Streamlined process for managing non-PreCat products

### 6.2 Technical Success Metrics
- Successful integration with minimal disruption to operations
- Data accuracy between systems at 99%+
- System performance meeting or exceeding requirements
- User adoption of the new tools and workflows

## 7. Constraints and Assumptions

### 7.1 Constraints
- Project must be operational before the seasonal peak (March 20)
- Limited IT resources available from Porrettana Gomme
- Must integrate with existing systems with minimal changes to operational systems
- Security requirements must be addressed in collaboration with ngbit

### 7.2 Assumptions
- Porrettana Gomme will provide access to necessary systems and data
- PreCat data structures will remain stable during implementation
- Business users will be available for testing and feedback
- The existing management system provides sufficient APIs or data export capabilities

## 8. Change Management

### 8.1 Training Requirements
- System administration training for IT staff
- End-user training for pricing and catalog management
- Analytics training for business users

### 8.2 Documentation
- User manuals for each module
- Technical documentation for integration points
- Process documentation for catalog and pricing management

## 9. Risk Management

### 9.1 Identified Risks
- Tight implementation timeline before seasonal peak
- Data quality issues in existing systems
- Integration complexity with legacy systems
- Resource constraints for implementation
- User adoption challenges

### 9.2 Risk Mitigation Strategies
- Prioritize core functionality for initial implementation
- Implement data quality checks early in the process
- Establish clear communication channels between technical teams
- Involve end-users in design and testing phases
- Create fallback procedures for critical business processes

## 10. Approval

This Business Requirements Document requires approval from:

- Marco Gandolfi (Porrettana Gomme) - Business Approval
- Andrea Alberici (Evolutivo) - Technical Approval
- Davide Castioni (Evolutivo) - Implementation Approval

Date: March 18, 2025

---

## Appendix A: Entity-Relationship Diagram

<$mermaid>
graph LR
    %% Entity definitions
    Product["Product
    ---
    product_id PK
    name
    description
    manufacturer_code
    product_code
    ean_code
    tire_size
    category
    vehicle_type
    manufacturer
    brand
    has_precat
    created_date
    modified_date
    is_active
    is_obsolete
    source_system
    precat_id"]
    Pricebook["Pricebook
    ---
    pricebook_id PK
    name
    description
    valid_from
    valid_to
    is_active
    currency
    includes_vat
    list_type"]
    PriceDetails["PriceDetails
    ---
    price_details_id PK
    pricebook_id FK
    product_id FK
    list_price
    purchase_price
    markup_percentage
    effective_date
    expiry_date
    quantity_limit
    location_code
    customer_segment
    geography"]
    ProductAssociation["ProductAssociation
    ---
    association_id PK
    from_product_id FK
    to_product_id FK
    association_type
    match_level
    is_default
    notes"]
    ProductStat["ProductStat
    ---
    stat_id PK
    product_id FK
    period_date
    sales_quantity
    sales_value
    margin_value
    margin_percentage"]
    %% Relationships
    Product --> |"from (1)"| ProductAssociation
    Product --> |"to (1)"| ProductAssociation
    Product --> |"priced in (1)"| PriceDetails
    Pricebook --> |"contains (1)"| PriceDetails
    Product --> |"measured by (1)"| ProductStat
</$mermaid>


## Appendix B: Integration Points

### B.1 Data Exchange Formats
- XML/Flat file formats for bulk data exchange
- SQL views for direct database access (read-only)
- Web service endpoints for real-time data retrieval

### B.2 System Interface Diagram

<$mermaid>
flowchart TD
    PG[Porrettana Gomme System]
    EV[Evolutivo Platform]
    BI[Business Intelligence Module]
    FW[Firewall/Security Layer]
    PG -->|Product Data| FW
    FW -->|Secure Channel| EV
    PG -->|Sales Data| FW
    FW -->|Analytics Data| BI
    EV -->|Price Updates| FW
    FW -->|Price Lists| PG
    EV -->|Analytics| BI
</$mermaid>

## Appendix C: Core Requirements Priority Matrix

| Requirement | Priority | Complexity | Phase |
|-------------|----------|------------|-------|
| Product Catalog Integration | High | Medium | 1 |
| Price List Management (Listino 90) | High | Medium | 1 |
| Obsolete Product Handling | High | Medium | 1 |
| Non-PreCat Product Management | High | High | 1 |
| Dynamic Price Updates | Medium | High | 2 |
| Product Association/Equivalence | Medium | High | 2 |
| Analytics Dashboard | Medium | Medium | 2 |
| Location-specific Pricing | Low | Medium | 3 |
| Customer Segment Pricing | Low | High | 3 |
| B2B E-commerce Integration | Low | High | 3 |