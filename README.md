# mediumNoMorePremium
This script is dedicated to those distracted people like me who don't want to lose the 5 premium articles due to missclicks so to avoid that, the premium elements are blurry to make them stand out

Copy this script, open medium (duh) from **Chrome/Firefox : press <em>ctrl+shift+i</em> or Menu>More Tools>Development Tools** and paste it into the console.
Ps: remember that you have to do this manually everytime you close the browser, until i have the time to make the extension lol 

Script:


const noMorePremium = ()=> {
	let targetDiv = document.querySelector(".star-15px_svg__svgIcon-use").parentNode.parentNode.parentNode.parentNode.parentNode.parentNode.parentNode;
	let cnDiv = targetDiv.className.replace(/ /g, ".")
	let elPrem = document.querySelectorAll('.'+ cnDiv);
	for (let i = 0; i < elPrem.length; i++) {
		if (elPrem[i].innerHTML.includes("star-15px_svg__svgIcon-use")) {
			elPrem[i].style.filter = "blur(1px)";
			elPrem[i].style.opacity = "0.8";
		}
		else {
			elPrem[i].style.borderLeft = "solid";
			elPrem[i].style.borderColor = "black";
			elPrem[i].style.borderRadius = "8px";
		}
	}
};
noMorePremium();
document.addEventListener("scroll", noMorePremium);
