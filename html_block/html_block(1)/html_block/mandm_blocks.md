This repository contains block references for MandM project for creating fully responsive, cross-client compatible email campaigns.

## ⚠️ General Styling

1. Each element should be built by using short code to call for the block by using correct ID and use of proper parameters that are defined for every block

## SOLO IMAGE

**Description**: This block is part of almost every email communications. It is a single, full-width row that contains the image. It is designed to render IMAGE on full width of the email with a possibility to define different image for mobile devices for a better responsivity. 

### Short code for the block:

#### For the email:
{# SOLO IMAGE #}{{ block("63285fb40d24507cae8eb947", {"BACKGROUND":"BACKGROUND_PLACEHOLDER","IMAGE_DESKTOP":"IMAGE_DESKTOP_PLACEHOLDER","IMAGE_MOBILE":"IMAGE_MOBILE_PLACEHOLDER","IMAGE_ALT":"ALT_TEXT_PLACEHOLDER","URL":"URL_PLACEHOLDER"}) }}

#### Formated for view:
```python
{# SOLO IMAGE #}
  {{ block("63285fb40d24507cae8eb947", {
    "BACKGROUND":"BACKGROUND_PLACEHOLDER",
    "IMAGE_DESKTOP":"IMAGE_DESKTOP_PLACEHOLDER",
    "IMAGE_MOBILE":"IMAGE_MOBILE_PLACEHOLDER",
    "IMAGE_ALT":"ALT_TEXT_PLACEHOLDER",
    "URL":"URL_PLACEHOLDER"
  }) }}
```

### ID and parameters
- ID = 63285fb40d24507cae8eb947 -> The ID is used as first element in the code without the name of the parameter
- BACKGROUND_PLACEHOLDER -> Data type: `String - Hex Color`. The background color behind the element. Default value is white (`#ffffff`) because the images are non-transparent, full-width, so the background is not that important most of the time.
- IMAGE_DESKTOP_PLACEHOLDER -> Data type: `String`. The direct URL of the hosted image file. Example: https://resources.mandmdirect.com/content/emails/2025/Automation/Monday/Monday_Week4.gif 
- IMAGE_MOBILE_PLACEHOLDER -> Data type: `String`. The direct URL of the hosted image file. Example: https://resources.mandmdirect.com/content/emails/2025/Automation/Monday/Monday_Week4.gif If IMAGE_MOBILE is not defined, there is only ONE image link for this block, leave the IMAGE_MOBILE_PLACEHOLDER empty OR put simple x symbol instead
- ALT_TEXT_PLACEHOLDER - Data type: `String`. Accessible text description of the image content. Example: Under £20
- URL_PLACEHOLDER - Data type: `String`. The destination link when the user clicks on the image. Example: https://www.mandmdirect.com/01/under-twenty

## SPACER

**Description**: The Spacer block is a utility component used to insert vertical space between other content blocks (e.g., between an image and a text block). It ensures consistent spacing across all email clients, including those that ignore standard CSS padding or margins.

### Short code for the block:

#### For the email:
{# SPACER #}{{ block("632867c50ffb643df2e9daa9", {"BACKGROUND":"BACKGROUND_PLACEHOLDER","HEIGHT":"HEIGHT_PLACEHOLDER"}) }}

#### Formated for view:
```python
{# SPACER #}
  {{ block("632867c50ffb643df2e9daa9", {
    "BACKGROUND":"BACKGROUND_PLACEHOLDER",
    "HEIGHT":"HEIGHT_PLACEHOLDER"
  }) }}
```

### ID and parameters
- ID = 632867c50ffb643df2e9daa9 -> The ID is used as first element in the code without the name of the parameter
- BACKGROUND_PLACEHOLDER -> Data type: `String`. The background color behind the element. Default value is white (`#ffffff`) because the background of the whole email is mostly white. But can be changed when trying to increase the space between two colored sections.
- HEIGHT_PLACEHOLDER -> Data type: `String`. The parameter defines how much extra space should be added. Default value is `5`.

## ONE BUTTON

**Description**: The Spacer block is a utility component used to insert vertical space between other content blocks (e.g., between an image and a text block). It ensures consistent spacing across all email clients, including those that ignore standard CSS padding or margins.

### Short code for the block:

#### For the email:
{# ONE BUTTON #}{{ block("66697c6e3638f5dd4ae716f7", {"BORDER_SIZE": BORDER_SIZE_PLACEHOLDER, "BTN_BORDER": "BTN_BORDER_PLACEHOLDER", "BTN_TEXT_COLOR": "BTN_TEXT_COLOR_PLACEHOLDER", "BACKGROUND": "BACKGROUND_PLACEHOLDER", "BTN_BACKGROUND": "BTN_BACKGROUND_PLACEHOLDER", "FONT_WEIGHT": "FONT_WEIGHT_PLACEHOLDER", "TEXT": "TEXT_PLACEHOLDER", "URL": "URL_PLACEHOLDER", "SPACE_AFTER": SPACE_AFTER_PLACEHOLDER}) }}

#### Formated for view:
```python
{# ONE BUTTON #}
  {{ block("66697c6e3638f5dd4ae716f7", {
    "BORDER_SIZE": BORDER_SIZE_PLACEHOLDER,
    "BTN_BORDER": "BTN_BORDER_PLACEHOLDER",
    "BTN_TEXT_COLOR": "BTN_TEXT_COLOR_PLACEHOLDER",
    "BACKGROUND": "BACKGROUND_PLACEHOLDER",
    "BTN_BACKGROUND": "BTN_BACKGROUND_PLACEHOLDER",
    "FONT_WEIGHT": "FONT_WEIGHT_PLACEHOLDER",
    "TEXT": "TEXT_PLACEHOLDER",
    "URL": "URL_PLACEHOLDER",
    "SPACE_AFTER": SPACE_AFTER_PLACEHOLDER
  }) }}
```

### ID and parameters
- ID = 66697c6e3638f5dd4ae716f7 -> The ID is used as first element in the code without the name of the parameter
- BACKGROUND_PLACEHOLDER -> Data type: `String - Hex Color`. The background color behind the element. Default value is white (`#ffffff`) because the background of the whole email is mostly white. But can be changed when trying to increase the space between two colored sections.
- BTN_BACKGROUND_PLACEHOLDER -> Data type: `String - Hex Color`. The background color for the button itself. Default value is white (`#ffffff`) because button matches the background color most of the time and it is outlined only by using the border.
- BORDER_SIZE_PLACEHOLDER -> Data type: `Number`. Parameter that defines the size of the border for the button. Default value is `2`.
- BTN_BORDER_PLACEHOLDER -> Data type: `String - Hex Color`. Parameter that defines color of the border of the button. Default value is sort of black `#252525`.
- BTN_TEXT_COLOR_PLACEHOLDER -> Data type: `String - Hex Color`. Parameter that defines color of the border of the button. Default value is sort of black `#252525`. This color most of the time matches the color of the border so it gives a look of a button. 
- FONT_WEIGHT_PLACEHOLDER -> Data type: `String`. Parameter that defines font wieght of the text in the button that is going to render. The parameter can have on of the values: `normal|bold`. Default value is `normal`.
- TEXT_PLACEHOLDER -> Data type: `String`. Parameter that defines what should be rendered in the button as a copy so the customer knows where they will be redirected. Example: `Shop Now`.
- URL_PLACEHOLDER -> Data type: `String`. The destination link when the user clicks on the image. Example: https://www.mandmdirect.com/01/under-twenty
- SPACE_AFTER_PLACEHOLDER -> Data type: `Number`. Parameter that defines the extra spacing / padding below the button. Default value is `5`.

## QUICK LINKS

**Description**: The Quick Links block is to render personalized categories / brands to customers. The personalization is done in the block itself with some categories as fallback. 

### Short code for the block:

#### For the email:
{# GBP - Quick Links #}{{ block("6659ca8712de069690b7bc9b", {"NEW_IN_TEST": NEW_IN_TEST_PLACEHOLDER, "IMAGE_TYPE": "IMAGE_TYPE_PLACEHOLDER", "BORDER_SIZE": BORDER_SIZE_PLACEHOLDER, "BTN_BORDER": "BTN_BORDER_PLACEHOLDER", "BTN_TEXT_COLOR": "BTN_TEXT_COLOR_PLACEHOLDER", "BACKGROUND": "BACKGROUND_PLACEHOLDER", "BTN_BACKGROUND": "BTN_BACKGROUND_PLACEHOLDER"}) }}

#### Formated for view:
```python
{# GBP - Quick Links #}
  {{ block("6659ca8712de069690b7bc9b", {
    "NEW_IN_TEST": NEW_IN_TEST_PLACEHOLDER,
    "IMAGE_TYPE": "IMAGE_TYPE_PLACEHOLDER",
    "BORDER_SIZE": BORDER_SIZE_PLACEHOLDER,
    "BTN_BORDER": "BTN_BORDER_PLACEHOLDER",
    "BTN_TEXT_COLOR": "BTN_TEXT_COLOR_PLACEHOLDER",
    "BACKGROUND": "BACKGROUND_PLACEHOLDER",
    "BTN_BACKGROUND": "BTN_BACKGROUND_PLACEHOLDER"
  }) }}
```

### ID and parameters
- ID = 6659ca8712de069690b7bc9b -> The ID is used as first element in the code without the name of the parameter
- BACKGROUND_PLACEHOLDER -> Data type: `String - Hex Color`. The background color behind the element. Default value is white (`#ffffff`) because the background of the whole email is mostly white. But can be changed when trying to increase the space between two colored sections.
- BTN_BACKGROUND_PLACEHOLDER -> Data type: `String - Hex Color`. The background color for the button below images. Default value is white (`#ffffff`) because button matches the background color most of the time and it is outlined only by using the border.
- BORDER_SIZE_PLACEHOLDER -> Data type: `Number`. Parameter that defines the size of the border for the button. Default value is `2`.
- BTN_BORDER_PLACEHOLDER -> Data type: `String - Hex Color`. Parameter that defines color of the border of the button. Default value is sort of black `#252525`.
- BTN_TEXT_COLOR_PLACEHOLDER -> Data type: `String - Hex Color`. Parameter that defines color of the border of the button. Default value is sort of black `#252525`. This color most of the time matches the color of the border so it gives a look of a button. 
- NEW_IN_TEST_PLACEHOLDER -> Data type: `Boolean`. Parameter that defines if the NEW IN imagery should be part of the block. The data type of the parameter is BOOLEAN and therefore possible values are `True|False`. Default value is `False`.
- IMAGE_TYPE_PLACEHOLDER -> Data type: `String`. Parameter that defines which images should be used. There are TWO types of the images in the block and you can choose one of these values `EDITORIAL|LOGO`. Default value is `EDITORIAL`.

## ABANDONED CART BLOCK

**Description**: The Abandoned cart block is to render full-width banner that is with basket theme to remind customers that they probably have something in the basket and that it might be sold out soon, so they shouldn"t waste any more time.

### Short code for the block:

#### For the email:
{# GBP - Abandoned cart block in BAU #}{{ block("667299f91030b95884caa6de", {"SPACE_AFTER": SPACE_AFTER_PLACEHOLDER}) }}

#### Formated for view:
```python
{# GBP - Abandoned cart block in BAU #}
  {{ block("667299f91030b95884caa6de", {
    "SPACE_AFTER": SPACE_AFTER_PLACEHOLDER
  }) }}
```

### ID and parameters
- ID = 667299f91030b95884caa6de -> The ID is used as first element in the code without the name of the parameter
- SPACE_AFTER_PLACEHOLDER -> Data type: `Number`. Parameter that defines the extra spacing / padding below the button. Default value is `5`.
