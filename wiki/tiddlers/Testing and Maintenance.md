# Testing and Maintenance

## Testing the Decision Table

1. Test with various product configurations to ensure correct pricing
2. Verify that the rules are being evaluated in the expected order
3. Check edge cases, such as:
   - Products with attributes exactly at the boundaries of ranges
   - Products that should match default rules
   - Products with special parameters like misura2 or extraparam

## Maintaining the Decision Table

### Updating Rules

When pricing rules change:
1. Simply update the records in the ProductCatalog module
2. No need to modify the Business Map unless the logic structure changes

### Adding New Rules

To add new rules:
1. Create new records in the ProductCatalog module
2. Assign appropriate sequence numbers to maintain the correct evaluation order
3. Test the new rules to ensure they work as expected

### Structural Changes

For structural changes to the decision process:
1. Update the Decision Table Map XML
2. Modify the ProductCatalog module structure if needed
3. Update existing records to match the new structure

## Performance Considerations

- Keep the number of rules manageable to ensure efficient processing
- Use appropriate indexing on the ProductCatalog module fields
- Consider caching frequently used decision results for better performance