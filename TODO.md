# Contributor Summary Endpoint - Implementation TODO

## Approved Plan Summary

Add GET /api/campaigns/:id/contributors endpoint returning grouped contributor totals with refunded status. SQL GROUP BY contributor. 404 for invalid ID. Empty [] for no pledges. Document in README.md.

## Implementation Steps

### 1. Backend Types (campaign.ts or new)

- Add ContributorSummary interface
- [x] Edit frontend/src/types/campaign.ts

### 2. Backend Data Layer (campaignStore.ts)

- Add ContributorSummary interface, getContributorSummary function with GROUP BY SQL
- [x] Edit backend/src/services/campaignStore.ts

### 3. Backend Route (index.ts)

- Added GET /api/campaigns/:id/contributors route + getContributorSummary import
- [x] Edit backend/src/index.ts

### 4. Document Response (README.md)

- Added API reference with response shape
- [x] Edit README.md

### 5. Frontend API + Component (if needed)

- Add listCampaignContributors(id): Promise<ContributorSummary[]>
- Hook up ContributorSummary component if exists
- [ ] Edit frontend/src/services/api.ts
- [ ] Edit frontend/src/components/ContributorSummary.tsx (if relevant)

### 6. Testing

- Backend: curl /api/campaigns/1/contributors → array, /api/invalid → 404
- Verify empty [], refunded status correct
- Frontend: manual test in dev
- Update TODO

## Progress

Ready for implementation.
