# Decision Table Map XML Structure

The Decision Table is defined using a Business Map in coreBOS. Below is the XML structure for this map:

```xml
<?xml version="1.0"?>
<decision>
    <hitPolicy>U</hitPolicy> 
    <rules>
        <rule>
            <sequence>1</sequence>  
            <decisionTable>
                <module>ProductCatalog</module>
<orderby>sequence</orderby>
                <searches>
                    <search>
                        <condition>
                            <input>brand</input>
                            <operation>e</operation>
                            <field>brand</field>
                        </condition>
                        <condition>
                            <input>vehicle_segment_type</input>
                            <operation>e</operation>
                            <field>vehicle_segment_type</field>
                        </condition>
                        <condition>
                            <input>rim_size</input>
                            <operation>e</operation>
                            <field>rim_diameter</field>
                        </condition>
                        <condition>
                           <input>misura_prod</input>
                           <operation>l</operation>
                          <field>width_min</field>
                       </condition>
                      <condition>
                           <input>misura_prod</input>
                           <operation>g</operation>
                           <field>width_max</field>
                     </condition>
                    </search>
                </searches>
                <output>markup_percentage</output>
            </decisionTable>
            <output>FieldValue</output>
        </rule>
    </rules>
</decision>
```

This map defines how the decision table works, including which fields to compare and what operators to use for comparison.

