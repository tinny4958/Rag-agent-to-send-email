# Rag-agent-to-send-email
An n8n workflow that uses an AI agent to process information via webhooks, send necessary emails, and record data in Google Sheets
First, a Webhook node receives incoming POST requests containing user details like name, email, phone number, and a query.

Next, an AI Agent processes that query using a system message to act as a helpful course assistant.

To find the answers, the agent connects to a Pinecone Vector Store with the index name "tinny," supported by OpenAI Embeddings.

Once the AI generates the response, it’s sent back through a Respond to Webhook node.

Finally, a Gmail node sends the response to your email address, and a Google Sheets node appends the user’s information and their question to your specified sheet.
