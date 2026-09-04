SWEDISH WORD TRAINER CLOUD - PASSWORD VERSION

Changes:
- Email + password authentication
- Separate Sign in and Create account buttons
- No magic link needed for normal sign-in
- Existing cloud word_lists table is unchanged

SUPABASE SETUP
1. Authentication -> Providers -> Email
2. Make sure Email provider is enabled.
3. Decide whether "Confirm email" should be enabled.
   - ON: new accounts get one confirmation email before first normal sign-in.
   - OFF: new accounts can usually sign in immediately.
4. Keep your existing Project URL and publishable key in config.js.
5. If you already ran setup.sql before, you do not need to run it again.

IMPORTANT FOR AN EXISTING MAGIC-LINK USER
An account created through passwordless magic-link login may not have a password set.
The simplest clean route is either:
- create a password-enabled account using "Create account", or
- use Supabase's password recovery/update flow to set a password for the existing user.

Your existing word lists belong to the existing Supabase user ID, so creating a totally
new user with a different email/account will not automatically inherit that user's lists.
