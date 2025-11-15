# CVD-App deployment guide

## Render (free tier) + Supabase
1. Push code (including ender.yaml) to GitHub.
2. Create a Web Service on https://render.com linked to this repo.
3. Render reads ender.yaml: build pip install -r requirements.txt, start python app.py.
4. Add environment variables:
   * SUPABASE_URL=postgresql://postgres.bpcrrwgpwloehbnmmehn:<password>@aws-1-ap-southeast-1.pooler.supabase.com:5432/postgres
   * Gmail keys (GMAIL_CLIENT_ID_SEND, ...), GOOGLE_CLIENT_ID, SECRET_KEY, etc.
5. Deploy.

Remember to update pp.py connection logic to use psycopg2 with SUPABASE_URL.
