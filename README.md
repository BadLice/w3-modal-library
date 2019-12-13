#Example

```
import React, { useState,useEffect,useRef } from "react";

import W3Modal from "../W3Modal.js"

export default function Editing(props) {
    const [isSectionModalOpen,setIsSectionModalOpen] = useState(false); //REQUIRED

    return (
        <div>

            <div className="w3-bar w3-grey">
                
                <W3Modal
                    setIsOpen = {setIsSectionModalOpen} //REQUIRED => set to false to close, set to true to open
                    isOpen = {isSectionModalOpen} //REQUIRED => true when is open, false when is close
                    btnClassName = "w3-bar-item w3-button w3-right w3-red" //can be everything
                    btnText = "Add category"
                    header="Add category" //can be a react element
                    headerClassName="w3-red w3-center" //can be everything
                    content = { //can be a react element
                        <NewSectionPusher functions={props.functions} states={props.states} isOpen={isSectionModalOpen} setIsOpen={setIsSectionModalOpen}/>
                    }
                    footer="Add" //can be a react element
                    footerClassName="w3-red w3-center" //can be everything
                />
            </div>
        </div>
    );
	
}
```