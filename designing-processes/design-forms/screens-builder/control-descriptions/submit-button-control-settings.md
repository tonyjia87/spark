---
description: >-
  Add a Submit Button control from which the form user can submit a form as part
  of a Request.
---

# Submit Button Control Settings

## Control Description

The Submit Button control adds a button from which the form user can submit the form as part of a Request. After using the Submit Button control, the form user cannot revise that form because the information included in the ProcessMaker Screen is sent to the next step in the Request.

{% hint style="info" %}
This control is not available for [Display](../types-for-screens.md#display)-type ProcessMaker Screens. See [Screen Types](../types-for-screens.md).
{% endhint %}

## Add the Control to a ProcessMaker Screen <a id="add-the-control-to-a-processmaker-screen"></a>

Follow these steps to add this control to the ProcessMaker Screen:

1. View the ProcessMaker Screen page to which to add the control.
2. Go to the **Controls** panel on the left side of the ProcessMaker Screen.
3. Drag the **Submit Button** icon![](../../../../.gitbook/assets/submit-button-control-screens-builder-processes.png)from the **Controls** panel anywhere within the ProcessMaker Screen canvas represented by the dotted-lined box. Existing controls on the ProcessMaker Screen canvas adjust positioning based on where you drag the control.
4. Drop into the ProcessMaker Screen where you want the control to display on the page.  

   ![](../../../../.gitbook/assets/submit-button-control-placed-screens-builder-processes.png)

Below is a Submit Button control in Preview mode.

![Submit Button control in Preview mode using the &quot;Primary&quot; Variant option](../../../../.gitbook/assets/submit-button-control-preview-screens-builder-processes.png)

## Inspector Settings <a id="inspector-settings"></a>

{% hint style="info" %}
See [View the Inspector Panel](../view-the-inspector-pane.md) for information how to view the **Inspector** panel.
{% endhint %}

Below are Inspector settings for the Submit Button control:

* **Field Name:** Specify the internal data name of the control that only the Process Owner views at design time. This is a required setting.
* **Field Label:** Specify the field label text that displays. **New Submit** is the default value.
* **Field Value:** Specify any alphanumeric value that the Submit Button control sends when the form user selects the button. This value can be evaluated in a rule.
* **Variant:** Specify the style for the Submit Button control. The style changes the control's appearance but otherwise has no functional difference. Select from the following options:
  * **Primary:** Blue-colored background with white-colored **Field Label** text. Set as the default.
  * **Secondary:** Gray-colored background with white-colored **Field Label** text.
  * **Success:** Green-colored background with white-colored **Field Label** text.
  * **Danger:** Red-colored background with white-colored **Field Label** text.
  * **Warning:** Yellow-colored background with black-colored **Field Label** text.
  * **Info:** Teal-colored background with white-colored **Field Label** text.
  * **Light:** White-colored background with black-colored **Field Label** text.
  * **Dark:** Black-colored background with white-colored **Field Label** text.
  * **Link:** White-colored background with blue-colored **Field Label** text.

## Related Topics <a id="related-topics"></a>

{% page-ref page="../types-for-screens.md" %}

{% page-ref page="../view-the-inspector-pane.md" %}

{% page-ref page="./" %}
