(function () {
  const copyText = function (domElement) {
    if (!navigator.clipboard) {
      domElement.dataset.toolTipContent = "Copying not supported";
    } else {
      const textToCopy = domElement.innerText;
      navigator.clipboard
        .writeText(textToCopy)
        .then(function () {
          domElement.dataset.tooltipContent = "Copied to clipboard";
        })
        .catch(function () {
          domElement.dataset.tooltipContent = "Copy failed";
        });
    }
  };

  const applyCopyTooltip = function (copyTooltipElement) {
    copyTooltipElement.addEventListener("mouseenter", function () {
      copyTooltipElement.dataset.tooltipContent = "Copy";
    });
    const copyTooltipText = function () {
      copyText(copyTooltipElement);
    };
    copyTooltipElement.addEventListener("click", copyTooltipText);
    copyTooltipElement.nextElementSibling.addEventListener(
      "click",
      copyTooltipText,
    );
  };

  document.querySelectorAll(".copy-tooltip").forEach(applyCopyTooltip);
  window.applyCopyTooltip = applyCopyTooltip;
})();
