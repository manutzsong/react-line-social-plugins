### LINE ADD FRIEND
######  For React

```javascript
import React, { useEffect } from "react";




export default function LineFriend() {
  const myRef = React.createRef();
  useEffect(() => {
    if (window.LineIt) {
      window.LineIt.loadButton();
    } else {
      const script = document.createElement("script");
      script.src =
        "https://d.line-scdn.net/r/web/social-plugin/js/thirdparty/loader.min.js";
      script.async = true;
      script.defer = true;
      myRef.current.appendChild(script);
      script.onload = function() {
        window.LineIt.loadButton();
        console.log(window.LineIt);
      };
    }
  }, []);

    return (
      <div ref={myRef}>
        <div 
        className="line-it-button" data-lang="en" data-type="friend" data-lineid="@ts1971" data-count="true" data-home="false" style={{display: "none"}}></div>
    </div>
    );
  
}
```
