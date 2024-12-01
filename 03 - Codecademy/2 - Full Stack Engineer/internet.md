# Creation of the Internet
- Precursor *ARPANET* created *1969*, funded by <u>US DoD</u>
	- Connected supercomputing centers run by <u>gov. agencies & universities</u>
	-> They wanted to connect their individual networks for <u>large-scale information transfer</u>
	- Followed different standards & technical implementations
	-> *1970*: *Transmission control protocol & internet protocol (TCP/IP)* were created to provide standards around <u>data transfer</u>
- <u>TCP/IP</u>: Researched throughout *1970s*, adopted in early *1980s*
	- Different networks adopted TCP/IP
	-> Formed interconnected global network of networks (Internet)
> [!info] Early ARPANET Institutions:
> *West coast*
> -> UCSB, SRI, UCLA, RAND, SDC, UTAH
> *East coast*
> -> MIT, BBM, Harvard
## The World Wide Web
- *Tim Berners-Lee* invented the world wide web in *1989*
- Collection of <u>interlinked websites</u> & <u>other web resources</u>
- Introduced user-friendly interface with <u>rise of web browsers</u> in *1990s*
	-> Enabled users to browse <u>multimedia content</u> & <u>interact with other users</u>
- Invention of world wide web
	=> Use of internet in wider society through *1990s*
	=> Creation of variety of websites that are still in use today\
## Browsers & Servers
- *Client-Server Model*
	- Client(User's device/Program) <u>makes request</u> for data
	- Server(Device/Program) <u>waits for incoming requests</u> & <u>sends back data</u>
- Server: In-house; Rented; Data center; Cloud server
### HTTP Status Codes
- Server's response to client includes specified status code
- Indicates <u>successful</u> or <u>non-successful(error)</u> HTTP request
	- Contains information about type of error that occurred

| Code                         | Explanation                                                         |
| ---------------------------- | ------------------------------------------------------------------- |
| 200<br>OK                    | The request has succeeded.                                          |
| 301<br>Moved Permanently     | The resource has been moved<br> and the client is being redirected. |
| 404<br>Not Found             | The requested resource<br> was not found.                           |
| 500<br>Internal Server Error | The server encountered an<br> unexpected error.                     | 
### Browsers
```mermaid
flowchart LR
1[Client: URL in Browser] -->|Request| 2[Server: Resources]
2 -->|HTML file| 1
```
- HTML file contains <u>links for assets/code</u> needed to display site properly
	-> More requests
		=> **CSS** stylesheet(s) | *Style & Layout* of web page | <u>Browser analyzes</u> CSS & <u>applies</u> visual styles to content of site
		=> **Website assets** | Images, Videos, etc. | Large -> Can lead to noticeable delay before rendered
		=> **JavaScript** file(s) | Makes webpage <u>interactive</u> | "Behavior" of web page | No JS: *Static* webpage
- Modern browsers request in parallel
## Web 2.0
- *Static websites*: Composed of <u>text, images & links with very little interactivity</u>
	- Static => Lack of movement => No change based on user behavior
- Progression of connection speeds & web technologies => More complex interactions made possible
- Cluster of web apps = "Web 2.0"
	-> <u>Dynamic user experience</u> | <u>Responsive</u> content without page reload required | Update selected regions of page
	-> <u>User-generated</u> content & <u>Social sharing</u> | Before content was widely authored by single person/entity
- *jQuery*: First JS-Framework that could fetch data while web page is running
- Rise of web frameworks connected to databases(Spring, Django, Ruby-on-Rails, etc.) => Efficient storing/creation/display of user-generated content
### Responsive Web Design
- Enabled by additions to <u>CSS</u>
	- Media Queries, relative units, etc.
 -> Adjustable presentation of websites based on size of window in which displayed
### Mobile
- App usage > Browsing
- Most mobile apps are internet connected, but not part of WWW
- Web is built out of links | Mobile apps are designed to keep user's attention
- Swift(iOS), JavaScript frameworks