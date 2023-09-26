For the utility to read, create and update records via the Hornbill API, it requires an API key to be securely stored alongside the client.

:::note
We recommend that you read the [API Key documentation](/esp-fundamentals/security/api-keys) and [best practice guide](/esp-fundamentals/best-practice/platform-api-keys) before creating API keys against your user records.
:::

### User

Every action within Hornbill must be performed in the context of a user account. As well as the chosen user account possessing the `User Import` role (see below) which facilitates the creation of the user accounts into the Hornbill platform, and the updating of user properties, the user account must possess roles for the applications that you are granting access to via the import utility. The above comment about roles refers to the [Hornbill Security Model](/esp-fundamentals/security/account-types) when associating roles with user accounts. This security  measure prevents you from inflating your session rights, or granting a user more rights than you have yourself.

:::important
We strongly recommend that you create a Service Account in your Hornbill instance, which can be used to perform the required API calls back into Hornbill.
:::

The service account that you create must be of type `User` (not `Basic`), and be granted the following roles:

- `User Import` - Allows the utility to create and update users, and associated records, in the Hornbill Platform.
- `Basic User Role` - Allows the utility to Core basic user roles.
- `Self Service User` - Allows the utility to assign Service Manager roles.
- `Board BPM Access` - Allows the utility to assign Board Manager roles.
- `Docmanager Portal` - Allows the utility to assign Document Manager roles.