;(function(window) {

  var svgSprite = '<svg>' +
    '' +
    '<symbol id="icon-jiantouxia" viewBox="0 0 1024 1024">' +
    '' +
    '<path d="M964.442162 315.495534 903.606163 255.993349 511.999488 647.667889 120.392814 255.993349 59.557838 315.495534 511.999488 768.004605Z"  ></path>' +
    '' +
    '</symbol>' +
    '' +
    '<symbol id="icon-wangpanyinle" viewBox="0 0 1024 1024">' +
    '' +
    '<path d="M933.751467 15.36 324.778667 16.196267c-35.969707 6.31808-59.306667 39.325013-59.306667 75.639467l0 115.094187-0.94208 0 0 539.828907c-27.661653-28.542293-55.927467-39.9872-91.96544-39.9872-86.695253 0-157.20448 70.15424-157.20448 156.40576 0 86.203733 70.509227 152.487253 157.20448 152.487253 82.64704 0 145.62304-58.361173 152.49408-148.40832l2.618027 0L327.676587 360.574293l626.305707 0.597333 0 316.22144c-25.7024-28.542293-53.101227-33.77152-88.849067-33.77152-86.074027 0-160.938667 69.632-160.938667 155.24864 0 85.613227 74.868053 155.286187 160.938667 155.286187 82.056533 0 150.534827-68.133547 149.589333-154.344107l0.6656 0L1015.38816 321.993387 1015.38816 151.21408 1015.38816 89.04704C1015.38816 40.05888 969.680213 15.568213 933.751467 15.36zM953.97888 299.554133 328.615253 298.789547 328.615253 146.223787c0-3.170987 2.307413-5.85728 5.40672-6.417067l612.287147-1.39264c0.382293-0.037547 0.768-0.105813 1.150293-0.105813 1.539413 0 3.034453 0.559787 4.191573 1.539413 1.49504 1.256107 2.331307 3.06176 2.331307 4.98688l0 59.026773L953.982293 299.554133z"  ></path>' +
    '' +
    '</symbol>' +
    '' +
    '</svg>'
  var script = function() {
    var scripts = document.getElementsByTagName('script')
    return scripts[scripts.length - 1]
  }()
  var shouldInjectCss = script.getAttribute("data-injectcss")

  /**
   * document ready
   */
  var ready = function(fn) {
    if (document.addEventListener) {
      if (~["complete", "loaded", "interactive"].indexOf(document.readyState)) {
        setTimeout(fn, 0)
      } else {
        var loadFn = function() {
          document.removeEventListener("DOMContentLoaded", loadFn, false)
          fn()
        }
        document.addEventListener("DOMContentLoaded", loadFn, false)
      }
    } else if (document.attachEvent) {
      IEContentLoaded(window, fn)
    }

    function IEContentLoaded(w, fn) {
      var d = w.document,
        done = false,
        // only fire once
        init = function() {
          if (!done) {
            done = true
            fn()
          }
        }
        // polling for no errors
      var polling = function() {
        try {
          // throws errors until after ondocumentready
          d.documentElement.doScroll('left')
        } catch (e) {
          setTimeout(polling, 50)
          return
        }
        // no errors, fire

        init()
      };

      polling()
        // trying to always fire before onload
      d.onreadystatechange = function() {
        if (d.readyState == 'complete') {
          d.onreadystatechange = null
          init()
        }
      }
    }
  }

  /**
   * Insert el before target
   *
   * @param {Element} el
   * @param {Element} target
   */

  var before = function(el, target) {
    target.parentNode.insertBefore(el, target)
  }

  /**
   * Prepend el to target
   *
   * @param {Element} el
   * @param {Element} target
   */

  var prepend = function(el, target) {
    if (target.firstChild) {
      before(el, target.firstChild)
    } else {
      target.appendChild(el)
    }
  }

  function appendSvg() {
    var div, svg

    div = document.createElement('div')
    div.innerHTML = svgSprite
    svgSprite = null
    svg = div.getElementsByTagName('svg')[0]
    if (svg) {
      svg.setAttribute('aria-hidden', 'true')
      svg.style.position = 'absolute'
      svg.style.width = 0
      svg.style.height = 0
      svg.style.overflow = 'hidden'
      prepend(svg, document.body)
    }
  }

  if (shouldInjectCss && !window.__iconfont__svg__cssinject__) {
    window.__iconfont__svg__cssinject__ = true
    try {
      document.write("<style>.svgfont {display: inline-block;width: 1em;height: 1em;fill: currentColor;vertical-align: -0.1em;font-size:16px;}</style>");
    } catch (e) {
      console && console.log(e)
    }
  }

  ready(appendSvg)


})(window)