# 🔗 LinkedIn Post Creator - Webhook Configuration

## Webhook Details

**Service:** n8n Cloud (Production)
**Status:** ✅ Active & Ready

---

## Webhook URL

```
https://lcharyfire1.app.n8n.cloud/webhook/b4aad059-001b-44cf-88bc-391451e2fc94
```

---

## Location in Code

**File:** `index.html`
**Line:** 447

```javascript
const WEBHOOK_URL = 'https://lcharyfire1.app.n8n.cloud/webhook/b4aad059-001b-44cf-88bc-391451e2fc94';
```

---

## Request Format

### **Method:** POST

### **Headers:**
```json
{
  "Content-Type": "application/json"
}
```

### **Body:**
```json
{
  "topic": "string - the LinkedIn topic/idea",
  "audience": "string - target audience selected by user"
}
```

### **Example:**
```json
{
  "topic": "AI in recruiting",
  "audience": "tech-professionals"
}
```

---

## Response Format

**Type:** Plain text (string)
**Content:** Generated LinkedIn post

**Example:**
```
AI is transforming how we recruit talent. Instead of keyword matching, we can now focus on cultural fit, growth potential, and team dynamics. What does your hiring process look like in the age of AI?
```

---

## Audience Options

The app supports these audience selections:

- `tech-professionals` - Tech Professionals
- `entrepreneurs` - Entrepreneurs & Founders
- `marketers` - Marketing Professionals
- `job-seekers` - Job Seekers & Career Changers
- `business-leaders` - Business Leaders & Executives
- `educators` - Educators & Trainers
- `sales-professionals` - Sales Professionals
- `product-managers` - Product Managers
- `designers` - UX/UI Designers
- `data-analysts` - Data Analysts & Scientists

---

## Testing the Webhook

### **Using cURL:**
```bash
curl -X POST https://lcharyfire1.app.n8n.cloud/webhook/b4aad059-001b-44cf-88bc-391451e2fc94 \
  -H "Content-Type: application/json" \
  -d '{
    "topic": "Remote work productivity",
    "audience": "business-leaders"
  }'
```

### **Using Postman:**
1. Method: POST
2. URL: `https://lcharyfire1.app.n8n.cloud/webhook/b4aad059-001b-44cf-88bc-391451e2fc94`
3. Headers: `Content-Type: application/json`
4. Body (raw JSON):
```json
{
  "topic": "Remote work productivity",
  "audience": "business-leaders"
}
```

---

## Error Handling

The app handles errors gracefully:

- **Empty topic:** Shows error message "Please enter a topic"
- **No audience selected:** Shows error message "Please select a target audience"
- **Webhook error:** Shows error message with details
- **Network error:** Displays user-friendly error message

---

## Monitoring

### **n8n Cloud Dashboard:**
1. Log in to https://n8n.io
2. Go to your workspace
3. Click on the LinkedIn Post Creator workflow
4. View "Executions" tab
5. Monitor real-time webhook calls

### **Metrics to Track:**
- Number of API calls per day
- Success rate (target: 99%+)
- Average response time (target: <3 seconds)
- Error rate (target: <1%)

---

## Rate Limiting

Currently no rate limiting is applied. For production scale, consider:

1. Adding rate limits in n8n workflow
2. Implementing API key authentication
3. Setting up usage quotas
4. Monitoring for abuse

---

## Webhook Status Checks

To check if webhook is active:

```bash
curl -X POST https://lcharyfire1.app.n8n.cloud/webhook/b4aad059-001b-44cf-88bc-391451e2fc94 \
  -H "Content-Type: application/json" \
  -d '{"topic": "test", "audience": "tech-professionals"}'
```

**Expected Response:** Generated LinkedIn post (200 OK)

---

## Updating the Webhook URL

If you need to change the webhook URL in the future:

1. Update line 447 in `index.html`
2. Redeploy to Cloudflare Pages
3. GitHub will auto-trigger new deployment

---

## Production Considerations

✅ **Already Implemented:**
- HTTPS only
- XSS protection
- Input validation
- Error handling

✅ **Recommended Additions:**
- Monitor webhook usage
- Set up alerts for high error rates
- Implement request logging
- Consider caching for common queries

---

**Webhook is production-ready!** ✅
