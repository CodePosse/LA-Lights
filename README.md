# LA-Lights
LA Dept of Street Lights


## Overview
The site is built with Twitter Bootstrap V 5.1.1, jQuery 3.6.0, and FontAwesome 5.15.4. jQuery and FontAwesome are called from a cloudflare CDN. Twitter dependencies are local.

## File structure
The file structure is semantic. This means CSS files are in css/, JavaScript is in js/, PDFs are in PDF/ and images are in img/ and images are also broken down to what section they are in eg: residents' section images are in img/residents/.

## ADA notes
Testing for the site was conducted with several industry-standard tools.

- [Wave](https://wave.webaim.org/extension/)
- [Lighthouse](https://developers.google.com/web/tools/lighthouse)
- [Accessibility Insights for Web](https://accessibilityinsights.io/docs/en/web/reference/help/)

### ADA and YouTube
In general the video itself needs to be close captioned, and it is not going to rely on in-page descriptions as captioning is timed to events in the video that we cannot detect or control.
- [UCLA's Notes on video compliance](https://socialmedia.ucla.edu/ada-compliance-video/)
- [Guide for captioning videos](https://morepro.com/make-youtube-videos-ada-compliant/)


## Modals
Most modals on the site start with a comment that tells you what is it. A comment looks like `<!--I'm a comment-->`

## Google Search/Form/Translate

### Search
Search is a copy-paste piece of code that is constructed and maintained through a Google control panel. You can create/maintain one here: https://programmablesearchengine.google.com/cse/all and then just add it by copy-pasting the code they give you. There are custom CSS Styles in the head of the search page.

```
<script async src="https://cse.google.com/cse.js?cx=a66f498654fed9e8a"></script>
<div class="gcse-search"></div>
```                        

## Form
The form is primarily used for Contact and it is inside an `iframe` that we copy-paste from Google. To build a form you can follow this link" https://support.google.com/a/users/answer/9308623?hl=en

It will look something like this: DO NOT USE THIS CODE, it does not go to a city email address, only a dummy address.
```
<iframe src="https://docs.google.com/forms/d/e/1FAIpQLSdiwDU1Wz4zdOfVkEf3ZfTbp0ChEaov6DeYdJYVunxwvHiH4Q/viewform?embedded=true" width="640" height="1081" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
```

```
<iframe src="https://docs.google.com/forms/d/e/1FAIpQLSdiwDU1Wz4zdOfVkEf3ZfTbp0ChEaov6DeYdJYVunxwvHiH4Q/viewform?embedded=true" width="640" height="1081" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
```

### Translate
There is a snippet of code on the site that also adds two classes to the search button. The function itself comes inside a modal.
```
<!-- Translate Modal -->
<div class="modal fade" id="googleTranslate" tabindex="-1" aria-labelledby="googleTranslateLabel" aria-hidden="true">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <h5 class="modal-title lablue1" id="googleTranslateLabel">Google Translate</h5>
                <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
            </div>
            <div class="modal-body lablue2">
                <div id="google_translate_element"></div>
            </div>
        </div>
    </div>
</div>
<script type="text/javascript">
    function googleTranslateElementInit() {
        new google.translate.TranslateElement({
            pageLanguage: 'en'
        }, 'google_translate_element');
    }
    $("button.gsc-search-button").addClass(["btn", "btn-primary"]);
</script>
<script type="text/javascript" src="//translate.google.com/translate_a/element.js?cb=googleTranslateElementInit"></script>
```

Calling the modal uses standard BootStrap modal

```
<a class="nav-link" data-bs-toggle="modal" href="#googleTranslate" role="button" aria-label="Translate">
    <i class="fas fa-language"></i>
    <span class="visually-hidden">Translate</span>
</a>
```