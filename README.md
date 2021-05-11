# MagicMirror1

var config = { 
  address: "localhost",
  port: 8080,
  basePath: "/",
  ipWhitelist: ["127.0.0.1 ", "::ffff:127.0.0.1", "::1"],

useHttps: false,
httpsPrivateKey: "",
httpsCertificate: "",

language: "en",
loglevel: ["INFO", "LOG", "WARN," "ERROR"], 
timeformat: 12,

units: "imperial",
modules: [
{
    module: "alert",
 },
 {
    module: "updatenotification",
    position: "top_bar"
 },
 {
    module: "clock",
    position: "top_left"
 },
 {
    module: "calendar",
    header: "US Holidays",
    position: "top_left",
    config: {
              calendars: [
                           {
                              symbol: "calendar-check",
                              url: "webcal://www.calendarlabs.com/ical/76/US_Holidays.ics"
                           }
                         ]
            }
  },
  {
      module: "compliments"
      position: "lower_third",
      config: 
              {
                updateInterval: 30000,
                compliments: 
                            {
                              morning: 
                                      [
                                       "Good morning",
                                       "Have a great day",
                                       "Mom this gift is for you."
                                      ],
                              afternoon:
                                        [
                                          "Your day is almost over.",
                                          "Reitirement is coming"
                                        ],
                              evening:
                                       [
                                        "Good Job mom and dad.",
                                        "Hope you guys had a great day!"
                                       ],
                              }
            }
     {
      module: "currentweather",
      position: "top_right",
      config: 
              {
                location: "mobile, US",
                locationID:"4076607",
                appleID: "596eecc6b502079d9d483547900e1f48"
              }
      }
             
     {
      module: "weatherforecast",
      position: "top_right",
      header: "Weather Forecast",
      config: 
              {
                location: "mobile, US",
                locationID:"4076607",
                appleID: "596eecc6b502079d9d483547900e1f48"
              }
     }
      
     {
      module: "newsfeed",
      position: "bottom_bar",
      config: 
              {
                feeds: 
                        {
                        title: "New York Times",
                        url: "https://rss.nytimes.com/services/xml/rss/nyt/HomePage.xml"
                        }
                   ],
                 showsourceTitle: true,
                 showPublishDate: true,
                 broadcastNewsFeeds: true,
                 broadcasNewsUpdate: true
               }
              },
              ]
     };
