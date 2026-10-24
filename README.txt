GoSwim Academy website

Project files
- index.html: responsive single-page website, English/Russian/Arabic translations,
  RTL presentation, booking form and client-side validation.
- goswim-logo.jpeg: academy logo.
- goswim-team-visual.png: hero image.
- goswim-profile-poster.png: specialist profile poster.

Preview
Keep the HTML and all three images in the same directory. Open index.html in a
browser to preview the design and language switching. A local file preview cannot
submit a booking; form submissions are processed by Netlify after deployment.

Booking form and required Netlify setup
The form is configured in index.html as a Netlify-detected form named
"goswim-booking". It sends the parent's name, email, phone, child's name and age,
swimming experience, preferred location (including a custom location when given),
preferred date and time, selected service, and additional message. No EmailJS
credentials or private keys are used.

Before accepting bookings:
1. Deploy this directory as the site's publish directory on Netlify. For a manual
   deploy, upload the complete directory (index.html and all three images) using
   Netlify's deploy UI. For a Git-connected site, commit/push the files and check
   that the publish directory contains index.html at its root.
2. In the Netlify site dashboard, open Forms > Form detection and select
   "Enable form detection" if it is disabled. Redeploy after enabling it so
   Netlify scans the updated HTML. Confirm that "goswim-booking" appears in the
   site's detected forms list.
3. Open Forms > Submission notifications and add an email notification for the
   "goswim-booking" form. Set the recipient to swimgo.academy@gmail.com and keep
   the submitted fields included in the email. The notification's Reply-to uses
   the parent's email address. The subject includes the Netlify submission ID.
   Netlify stores accepted submissions in the site's Forms area as a backup.
4. Submit a test booking from the published site using test contact details.
   Confirm that it appears in Netlify Forms and that the notification arrives at
   swimgo.academy@gmail.com. Check spam/quarantine if needed. If the test fails,
   disable or remove the form notification until it is fixed. Do not advertise
   email notifications as configured until the test message arrives.

The page only displays its success message after the Netlify form endpoint returns
an HTTP success response. If the service rejects the submission or is unavailable,
the page displays an error in the selected language and keeps the entered details.
