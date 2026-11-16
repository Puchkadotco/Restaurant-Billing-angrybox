# ANGRY BOX POS — starter build

A responsive React + Vite restaurant POS starter for three branches, expandable later.

## Included in this first build
- Owner overview and branch selector
- Three starter branches (Branch 1–3)
- Menu item management
- Billing cart and send-to-kitchen workflow
- Kitchen order status workflow
- Basic sales summaries by branch
- Local demo mode so you can test the interface immediately
- Supabase database schema for the online version

## Important before using with real customers
This is a first working prototype, not a production-ready cash register yet.
- Local demo mode stores data only in the current browser/device. It does not sync between devices.
- Online mode requires a Supabase project, database setup, authentication, and secure row-level security policies. The included schema enables RLS and deliberately does not add public access policies.
- Do not enter real customer data or rely on this for live billing until authentication, branch-level permissions, backups, taxes/GST, payment reconciliation, printer support, and security testing are completed.
- The current demo uses sample menu items and sample branch names; replace these with your real details.

## Run locally / in an online development workspace
1. Install Node.js 20 or newer.
2. In this project folder run `npm install`.
3. Run `npm run dev`.
4. Open the local preview URL shown by the workspace.

## Connect a Supabase project (developer setup)
1. Create a Supabase project.
2. Open SQL Editor and run `supabase/schema.sql`.
3. Add a `.env` file based on `.env.example`:
   - `VITE_SUPABASE_URL=...`
   - `VITE_SUPABASE_ANON_KEY=...`
4. Restart the development server.

The starter UI attempts to read/write Supabase tables when credentials exist. Because the schema enables RLS without public policies, a developer must first implement Supabase Auth and secure role/branch policies before cloud operations can work. Never put the Supabase `service_role` key in frontend code.

## Suggested next development stages
1. Supabase Auth: owner, branch manager, cashier, kitchen staff.
2. Branch membership and strict row-level data isolation.
3. Tax/GST configuration, discounts, payment methods and bill numbering.
4. Inventory ingredients, recipes, stock adjustments and inter-branch transfers.
5. Thermal receipt printing and kitchen printer/display refinements.
6. Backups, audit logs, export and deployment checks.
