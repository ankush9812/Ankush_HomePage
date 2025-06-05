# Citation Counts - Dynamic vs Static

## Current Implementation: Static (Hardcoded)

The citation counts on your homepage are currently **static** (hardcoded in the HTML). This means they won't update automatically when your Google Scholar profile changes.

### Current Stats (as of June 2025):
- **Citations**: 59
- **h-index**: 4
- **Publications**: 6
- **i10-index**: 4

## Options for Dynamic Citation Counts

### Option 1: Manual Updates (Current - Recommended for simplicity)
- **Pros**: Simple, reliable, no external dependencies
- **Cons**: Requires manual updates when stats change
- **How**: Edit the `data-target` attributes in `index.html`

### Option 2: Backend Service (Recommended for automation)
- **Pros**: Fully automated, always up-to-date
- **Cons**: Requires backend development
- **Implementation**: 
  - Create a backend API that scrapes Google Scholar
  - Call this API from the frontend
  - Update the stats dynamically

### Option 3: Client-side Scraping (Not Recommended)
- **Pros**: No backend required
- **Cons**: Blocked by CORS, unreliable, against Google's ToS
- **Status**: Not feasible due to browser security restrictions

## Recommended Approach

For your current needs, I recommend **Option 1 (Manual Updates)** because:

1. **Simplicity**: No complex setup required
2. **Reliability**: Always works, no API dependencies
3. **Performance**: Fast loading, no external requests
4. **Control**: You decide when to update the numbers

### How to Update Citation Counts Manually

1. **Check your Google Scholar profile** for updated stats
2. **Edit the HTML file** (`index.html`) around line 146-157:
   ```html
   <div class="stat-number" data-target="59">0</div>  <!-- Update this number -->
   ```
3. **Update all four stats**:
   - Citations
   - h-index
   - Publications count
   - i10-index

## Future Enhancement: Backend Service

If you want fully automated updates in the future, we can implement a backend service that:

1. **Scrapes Google Scholar** periodically (respecting rate limits)
2. **Stores the data** in a database
3. **Provides an API** for the frontend to fetch current stats
4. **Updates automatically** without manual intervention

This would require:
- Backend development (Node.js, Python, etc.)
- Hosting for the backend service
- Database for storing historical data
- Scheduled jobs for periodic updates

## Current Status

✅ **Static implementation** with timestamp showing when stats were last verified
✅ **Easy manual update process** documented
🔄 **Backend service** available as future enhancement

Let me know if you'd like to implement the automated backend solution!