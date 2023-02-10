# sms-intent
Sample application for creating an SMS intent that should be handled by the default SMS sender application in the system.
Based on the official documentation of Common intents: https://developer.android.com/guide/components/intents-common#Messaging

The main point is this function:

    private fun composeSmsMessage(message: String) {
        val intent = Intent(Intent.ACTION_SENDTO).apply {
            data = Uri.parse("smsto:")  // This ensures only SMS apps respond
            putExtra("sms_body", message)
        }
        startActivity(intent)
    }
