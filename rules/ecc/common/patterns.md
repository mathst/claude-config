# Common Patterns

## Skeleton Projects

Build new thing:
1. Hunt battle-tested skeleton project
2. Parallel agents judge options:
   - Security check
   - Extensibility check
   - Relevance score
   - Build plan
3. Clone best one as base
4. Iterate inside proven structure

## Design Patterns

### Repository Pattern

Hide data access behind one steady interface:
- Standard ops: findAll, findById, create, update, delete
- Concrete impl handle storage detail (database, API, file, etc.)
- Business logic lean on abstract interface, not storage
- Swap data source easy, mock easy in test

### API Response Format

Same envelope for all API response:
- Success/status flag
- Data payload (null on error)
- Error message field (null on success)
- Metadata for paginated response (total, page, limit)