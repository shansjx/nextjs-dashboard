# nextjs-dashboard 
 A project following the Next.js tutorial
## Login User
 email: user@nextmail.com </br>
 password: 123456
## Issues
### Vercel Deployment fails (Chapter 10) - comment out ppr: incremental
<em>/next.config.mjs</em>
```javascript
/** @type {import('next').NextConfig} */

const nextConfig = {
    // experimental: {
    //     ppr: 'incremental',
    //   },
};

export default nextConfig;
```
### Client-side validation aria labels (Chapter 14) - wrong error type
<em>/app/lib/actions.ts</em>
```diff
const FormSchema = z.object({
  id: z.string(),
  customerId: z.string({
-   invalid_type_error: 'Please select a customer.',
+   required_error: 'Please select a customer.',
  }),
  amount: z.coerce
    .number()
    .gt(0, { message: 'Please enter an amount greater than $0.' }),
    status: z.enum(['pending', 'paid'], {
-   invalid_type_error: 'Please select an invoice status.',
+   required_error: 'Please select an invoice status.',
  }),
///
```

## References
 [Tutorial used](https://nextjs.org/learn/dashboard-app/)
