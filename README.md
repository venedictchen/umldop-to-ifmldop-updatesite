# UML-DOP to IFML-DOP

An Eclipse plugin that transforms a **UML-DOP** model into an **IFML-DOP** model.

Part of the Prices-IDE toolchain (Software Product Line Engineering with Delta-Oriented Programming and Model-Driven Software Engineering).

| | |
|---|---|
| Plugin ID | `id.ac.ui.cs.prices.umldop.to.ifmldop` |
| Feature ID | `id.ac.ui.cs.prices.umldop.to.ifmldop.feature` |
| Version | `1.0.0` |
| Update site | https://github.com/venedictchen/umldop-to-ifmldop-updatesite |

---

## Requirements

Before installing, make sure you have:

- **Eclipse IDE** (Eclipse Modeling Tools is recommended, since it already bundles EMF)
- **Java 11** or newer
- **EMF (Eclipse Modeling Framework)** runtime
- The **UML-DOP** and **IFML-DOP** metamodels / editors installed in the same Eclipse instance

> If you use the Prices-IDE Eclipse distribution, the metamodels are already present and you only need to install this plugin.

---

## Installation

There are two ways to install. Pick whichever you prefer.

### Option A: Install from the update site (recommended)

1. Open Eclipse.
2. Go to **Help → Install New Software…**
3. Click **Add…** and fill in:

   - **Name:** `UML-DOP to IFML-DOP`
   - **Location:**
     ```
     https://raw.githubusercontent.com/venedictchen/umldop-to-ifmldop-updatesite/main/
     ```

4. Click **Add**, then select the **UML-DOP-TO-IFML-DOP** category in the list.
5. Check the feature, then click **Next → Next**.
6. Accept the license and click **Finish**.
7. When Eclipse warns about unsigned content, click **Install anyway**.
8. Restart Eclipse when prompted.

### Option B: Install from a local copy

Use this if you are offline or behind a proxy.

1. Download the update site repository as a ZIP:
   `https://github.com/venedictchen/umldop-to-ifmldop-updatesite` → **Code → Download ZIP**
2. Extract it anywhere on your machine.
3. In Eclipse, go to **Help → Install New Software… → Add…**
4. Click **Local…** and select the extracted folder (the one containing `content.jar`, `artifacts.jar`, and `site.xml`).
5. Follow steps 4 to 8 from Option A.

### Verifying the installation

Go to **Help → About Eclipse IDE → Installation Details → Installed Software** and confirm that
`UML-DOP to IFML-DOP` appears in the list.

---

## Usage

1. Open your project in the **Project Explorer**.
2. Locate the UML-DOP model file you want to transform.
3. **Right-click** the model file.
4. Choose **Transform UML-DOP to IFML-DOP** from the context menu.
5. Wait for the transformation to finish. Progress is shown in the Eclipse status bar.
6. The generated IFML-DOP model is written next to the source model in the same folder.
7. If the new file does not appear, select the project and press **F5** to refresh.

You can open the result with the IFML-DOP editor to inspect or continue editing it.

---

## Troubleshooting

**The context menu entry does not appear**
Make sure you right-clicked the model file itself, not the containing folder. Also confirm the plugin is listed under *Installed Software*.

**"No repository found at …" when adding the update site**
Check that the URL ends with a slash and points to `raw.githubusercontent.com`, not `github.com`. Alternatively use Option B.

**Installation fails with a missing dependency**
Your Eclipse is missing EMF or one of the metamodels. Install **Eclipse Modeling Framework (EMF) - Runtime** via *Help → Install New Software…* using the release update site for your Eclipse version, then retry.

**The transformation fails or produces an empty model**
Open **Window → Show View → Error Log** and check the stack trace. Most failures come from a source model that does not validate against the UML-DOP metamodel.

---

## Updating and uninstalling

- **Update:** *Help → Check for Updates*
- **Uninstall:** *Help → About Eclipse IDE → Installation Details*, select the feature, then click **Uninstall…** and restart.

---

## Repositories

- Plugin source: https://github.com/venedictchen/uml-dop-to-ifml-dop
- Update site: https://github.com/venedictchen/umldop-to-ifmldop-updatesite

## Development

To build or modify the plugin:

1. Clone the source repository.
2. In Eclipse, use **File → Import → Existing Projects into Workspace** and select
   `id.ac.ui.cs.prices.umldop.to.ifmldop`.
3. Open `plugin.xml` and run the plugin with **Run As → Eclipse Application** to launch a test
   instance of Eclipse with the plugin loaded.