---
title: Zapobieganie obcinaniu tekstu w hierarchii stanowisk i eksportowanie do programu Visio
description: W tym temacie wyjaśniono, jak można rozwiązać problem polegający na tym, że nazwy stanowisk i imiona i nazwiska osób są obcinane, gdy odbiorcy wyświetlają hierarchię stanowisk w Microsoft Dynamics 365 for Talent. Obcinanie tekstu może utrudniać wykonywanie zrzutów ekranu lub wydrukowanie hierarchii.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 87d1c1994b14fac45fa305a9223ed45ee363a70c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518804"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a><span data-ttu-id="15b34-104">Zapobieganie obcinaniu tekstu w hierarchii stanowisk i eksportowanie do programu Visio</span><span class="sxs-lookup"><span data-stu-id="15b34-104">Avoid text truncation on the position hierarchy and export to Visio</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="15b34-105">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="15b34-105">**Issue**</span></span>

<span data-ttu-id="15b34-106">Gdy odbiorcy wyświetlają hierarchię stanowisk w Microsoft Dynamics 365 for Talent, nazwy stanowisk i imiona oraz nazwiska osób są obcinane.</span><span class="sxs-lookup"><span data-stu-id="15b34-106">When a customer views the position hierarchy in Microsoft Dynamics 365 for Talent, the names of individuals and positions are truncated.</span></span> <span data-ttu-id="15b34-107">Z tego względu może być trudne wykonanie zrzutu ekranu lub drukowanie i dystrybucja hierarchii.</span><span class="sxs-lookup"><span data-stu-id="15b34-107">Therefore, it can be difficult to take a screenshot, or to print and distribute the hierarchy.</span></span>

![Hierarchia stanowisk](media/position-h.png)

<span data-ttu-id="15b34-109">**Przyczyna**</span><span class="sxs-lookup"><span data-stu-id="15b34-109">**Cause**</span></span>

<span data-ttu-id="15b34-110">Jest to celowe.</span><span class="sxs-lookup"><span data-stu-id="15b34-110">This behavior is by design.</span></span>

<span data-ttu-id="15b34-111">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="15b34-111">**Resolution**</span></span>

<span data-ttu-id="15b34-112">Niestety użytkownicy nie mogą łatwo zmieniać rozmiaru tekstu.</span><span class="sxs-lookup"><span data-stu-id="15b34-112">Unfortunately, users can't easily change the size of the text.</span></span> <span data-ttu-id="15b34-113">Można jednak wyeksportować hierarchię stanowisk poza Talent i następnie zaimportować ją do programu Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="15b34-113">However, you can export the position hierarchy out of Talent and then import it into Microsoft Visio.</span></span> <span data-ttu-id="15b34-114">Mimo że następujący artykuł został napisany dla systemu Microsoft Dynamics AX 2012, proces można zastosować do opcji Talent: [eksportowanie hierarchii stanowisk do programu Microsoft Visio](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span><span class="sxs-lookup"><span data-stu-id="15b34-114">Although the following article was written for Microsoft Dynamics AX 2012, the process still applies to Talent: [Export a position hierarchy to Microsoft Visio](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span></span>

<span data-ttu-id="15b34-115">Wykonaj następujące kroki, aby wyeksportować do programu Visio.</span><span class="sxs-lookup"><span data-stu-id="15b34-115">Follow these steps to export to Visio.</span></span>

1. <span data-ttu-id="15b34-116">W programie Talent otwórz stronę listy **Stanowiska**.</span><span class="sxs-lookup"><span data-stu-id="15b34-116">In Talent, open the **Positions** list page.</span></span>

    <span data-ttu-id="15b34-117">Aby dołączyć więcej informacji w diagramie struktury organizacji, dodaj pola do listy **Stanowiska**, aby były one dostępne podczas korzystania z kreatora w dalszej części tej procedury.</span><span class="sxs-lookup"><span data-stu-id="15b34-117">To include more information in the organization structure diagram, add fields to the **Positions** list, so that they are available when you use the wizard later in this procedure.</span></span>

2. <span data-ttu-id="15b34-118">W okienku akcji naciśnij przycisk **Otwórz w programie Microsoft Office**, a następnie, w obszarze **Eksportuj do programu Excel**, wybierz opcję **Stanowiska**.</span><span class="sxs-lookup"><span data-stu-id="15b34-118">On the Action Pane, select the **Open in Microsoft Office** button, and then, under **Export to Excel**, select **Positions**.</span></span> <span data-ttu-id="15b34-119">Alternatywnie naciśnij klawisze Ctrl + T.</span><span class="sxs-lookup"><span data-stu-id="15b34-119">Alternatively, press Ctrl+T.</span></span>

    ![Eksportowanie strony listy Stanowiska do programu Microsoft Excel](media/org-admin.png)

3. <span data-ttu-id="15b34-121">Zapisz plik programu Excel, który został wyeksportowany.</span><span class="sxs-lookup"><span data-stu-id="15b34-121">Save the Excel file that is exported.</span></span>

    ![Okno dialogowe Eksportuj do programu Excel](media/export-excel.png)

4. <span data-ttu-id="15b34-123">W programie Visio zaznacz **Visio — Utwórz nowy**i wybierz kategorię szablonu **Służbowy**.</span><span class="sxs-lookup"><span data-stu-id="15b34-123">In Visio, select **Visio - Create New**, and select the **Business** template category.</span></span>

    ![Nowy diagram](media/new.png)

5. <span data-ttu-id="15b34-125">Wybierz **Kreatora schematów organizacyjnych**, a następnie wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="15b34-125">Select **Organization Chart Wizard**, and then select **Create**.</span></span>

    ![Okno dialogowe Kreator schematów organizacji](media/orgchart-wizard.png)

6. <span data-ttu-id="15b34-127">Wybierz **Informacje, które już są przechowywane w pliku lub bazie danych**, a następnie wybierz opcję **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="15b34-127">Select **Information that's already stored in a file or database**, and then select **Next**.</span></span>

    ![Kreator schematów organizacyjnych 1](media/orgchart-wizard7.png)

7. <span data-ttu-id="15b34-129">Wybierz **Tekst, Org Plus (\*.txt) lub plik programu Excel**, a następnie wybierz opcję **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="15b34-129">Choose **A text, Org Plus (\*.txt), or Excel file**, and then select **Next**.</span></span>

    ![Kreator schematów organizacyjnych 2](media/orgchart-wizard3.png)

8. <span data-ttu-id="15b34-131">Przeglądaj, aby wybrać wyeksportowany plik programu Excel zawierający hierarchię stanowisk, a następnie wybierz opcję **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="15b34-131">Browse to select the exported Excel file that contains the position hierarchy, and then select **Next**.</span></span>

    ![Kreator schematów organizacyjnych 3](media/orgchart-wizard2.png)

9. <span data-ttu-id="15b34-133">Ustaw pole **Nazwa** jako **Stanowisko**, ustaw pole **Podlega** jako **Stanowisko zwierzchnie**, a następnie wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="15b34-133">Set the **Name** field to **Position**, set the **Reports to** field to **Reports to position**, and then select **Next**.</span></span>

    ![Kreator schematów organizacyjnych 4](media/orgchart-wizard1.png)

10. <span data-ttu-id="15b34-135">Wybierz pola, które mają być pokazywane na każdym węźle, a następnie wybierz opcję **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="15b34-135">Select the fields that should be shown on each node, and then select **Next**.</span></span>

    ![Kreator schematów organizacyjnych 5](media/orgchart-wizard5.png)

11. <span data-ttu-id="15b34-137">Dodaj kolumnę **Stanowisko** do listy **pól danych kształtów**, a następnie wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="15b34-137">Add the **Position** column to the **Shape Data fields** list, and then select **Next**.</span></span>

    ![Kreator schematów organizacyjnych 6](media/orgchart-wizard6.png)

12. <span data-ttu-id="15b34-139">Obrazy nie są obecnie dostępne.</span><span class="sxs-lookup"><span data-stu-id="15b34-139">Pictures aren't currently available.</span></span> <span data-ttu-id="15b34-140">W związku z tym, na następnej stronie wybierz **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="15b34-140">Therefore, on the next page, select **Next**.</span></span>
13. <span data-ttu-id="15b34-141">Wybierz **Chcę użyć kreatora do automatycznego podzielenia schematu organizacyjnego na strony**.</span><span class="sxs-lookup"><span data-stu-id="15b34-141">Select **I want the wizard to automatically break my organization chart across pages**.</span></span>

    ![Kreator schematów organizacyjnych 7](media/orgchart-wizard4.png)

14. <span data-ttu-id="15b34-143">Wybierz **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="15b34-143">Select **Finish**.</span></span>

    <span data-ttu-id="15b34-144">Jeśli ma żadnych stanowisk, które nie znajdują się w strukturze, użytkownik jest proszony o uwzględnienie ich na diagramie.</span><span class="sxs-lookup"><span data-stu-id="15b34-144">If there are any positions that aren't in the structure, you're asked to include them in the diagram.</span></span>

<span data-ttu-id="15b34-145">Diagram, który jest generowany w programie Visio, zawiera każdego kierownika w oddzielnym arkuszu.</span><span class="sxs-lookup"><span data-stu-id="15b34-145">The diagram that is generated in Visio shows each manager on a separate worksheet.</span></span>

<span data-ttu-id="15b34-146">Na podstawie pól wybranych do uwzględnienia w schemacie, każdy węzeł wyświetla odpowiednie informacje podczas generowania pliku programu Visio.</span><span class="sxs-lookup"><span data-stu-id="15b34-146">Based on the fields that you selected to include in the diagram, each node shows the appropriate information when the Visio file is generated.</span></span>

![Diagram hierarchii](media/hierarchy.png)

<span data-ttu-id="15b34-148">**Opcja dodatkowa**</span><span class="sxs-lookup"><span data-stu-id="15b34-148">**Additional option**</span></span>

<span data-ttu-id="15b34-149">W opcji Talenty również można używać obszaru roboczego **osoby** w celu wyświetlenia niektórych informacji dotyczących hierarchii.</span><span class="sxs-lookup"><span data-stu-id="15b34-149">In Talent, you might also be able to use the **People** workspace to view some hierarchy-related information.</span></span>
