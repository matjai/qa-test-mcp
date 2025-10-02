
## Software QA Test

Goal: to be able to login to chatgu.mesiniaga.com.my and initiate simple chat.

view mode: desktop view

Pre-reqs: 
1. Chrome Browser launched
2. MS Auth initiated and user logged in once.

auth: username: ... and password: ...

Steps:
1. go to url chatgu.mesiniaga.com.my (hint: navigate to https://chatgu.mesiniaga.com.my/, main page displays with heading "Supercharge Your Productivity" as h1 element uid=22_5, page also shows "Log In" button uid=22_3 and "Get Started!" button uid=22_2)
2. click on login button on main nav menu (hint: button with text "Log In" in header navigation, uid=22_3 or uid=23_3, clicking navigates to login page showing "Welcome Back" heading uid=24_2, page displays email textbox uid=24_4, password textbox uid=24_5, and "Sign in with Microsoft" link uid=24_8)
3. on login page, click on "Sign in with Microsoft" (hint: link element with text "Sign in with Microsoft", uid=24_8, clicking shows authentication processing message "Successfully logged in" uid=25_1 and "Processing authentication..." uid=25_3, then redirects to Chat page with "Conversations" sidebar heading uid=26_1, chat input textbox "Ask Anything" uid=26_56, and heading "How can I help you today?" uid=26_55)
4. on Chat page, user user chat input and key in a query "Tell me a short explanation on using excel functions, 1 para long" (hint: textbox with placeholder "Ask Anything" uid=26_56 or uid=27_56, fill text and click submit button uid=27_60, query is submitted showing disabled input uid=28_56 and "Thinking" status, response appears with heading "Using Excel Functions" uid=30_63, full response text uid=30_64, new conversation appears in sidebar as "New Conversation" uid=30_5, chat input re-enabled uid=30_66, "New Chat" button enabled uid=30_2)