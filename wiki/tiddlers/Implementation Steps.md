# Implementation Steps

## 1. Create the ProductCatalog Module

Create this custom module in coreBOS with all the required fields as specified in the module structure documentation.

## 2. Create the Business Map

1. Go to Business Maps module
2. Create a new record with type "Decision Table"
3. Paste the XML from the Decision Table Map
4. Save the record

## 3. Populate the Decision Table

Add records to the ProductCatalog module based on your pricing rules, paying attention to the sequence for proper rule evaluation.

## 4. Implement Rule Evaluation

To use the decision table in your code or workflows:

```php
// Context with product attributes
$context = array(
    'brand' => 'PIRELLI',
    'vehicle_segment_type' => 'VETTURA', 
    'rim_diameter' => 15,
    'tire_width' => 200,  // Actual tire width
    'misura2' => '',      // Additional measurement if available
    'extraparam' => ''    // Extra parameter if needed
);

// Evaluate the decision table with the given context
$markup = coreBOS_Rule::evaluate('YourDecisionTableMapName', $context);

// $markup will contain the markup percentage (e.g., 36 for a 200mm width)
```
* TestMap feature :

> test record -> 
https://porrettana.evolutivo.it/index.php?module=cbMap&action=testMap&brand=H4&vehicle_segment_type=VETTURA&rim_size=15&misura_prod=2001&record=9269&

The test is made based on the : context variables, we put the values of the context variables based on the ProductCatalog rules created + map id.

Results: 
1. the output is shown 
2. the query generated based on the testmap url
3. the output __DoesNotPass__ is shown when the rules are not met or map is not correct

## 5. Create Automation Workflows

You can automate the pricing process by creating workflows that:
1. Trigger from the button on the PriceList Module (Sistema. Mass Actions.)
2. Prepare the context array with the appropriate values - > 
* Execute expression: setContext:  VARIABLE NAME: context field name on decision table
In this case: the variable get the value of the field from Product module 
3. Use the "Update fields" task to call the rule evaluation : evaluateRule(mapID)
4. Add the Business Action on DetailView as a Button to runBAWorkflow