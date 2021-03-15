---
title: Zapobieganie obcinaniu tekstu w hierarchii stanowisk i eksportowanie do programu Visio
description: W tym artykule wyjaśniono, jak można rozwiązać problem polegający na tym, że nazwy stanowisk i imiona i nazwiska osób są obcinane, gdy odbiorcy wyświetlają hierarchię stanowisk w Microsoft Dynamics 365 Human Resources. Obcinanie tekstu może utrudniać wykonywanie zrzutów ekranu lub wydrukowanie hierarchii.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0dc91d3165f14c165f75756dc63a3dc8f63149aa
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113842"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a>Zapobieganie obcinaniu tekstu w hierarchii stanowisk i eksportowanie do programu Visio

**Wystawienie**

Gdy odbiorcy wyświetlają hierarchię stanowisk w Microsoft Dynamics 365 Human Resources, nazwy stanowisk i imiona oraz nazwiska osób są obcinane. Z tego względu może być trudne wykonanie zrzutu ekranu lub drukowanie i dystrybucja hierarchii.

![Hierarchia stanowisk](media/position-h.png)

**Przyczyna**

Jest to celowe.

**Rozdzielczość**

Niestety użytkownicy nie mogą łatwo zmieniać rozmiaru tekstu. Można jednak wyeksportować hierarchię stanowisk poza moduł Human Resources i następnie zaimportować ją do programu Microsoft Visio. Mimo że następujący artykuł został napisany dla systemu Microsoft Dynamics AX 2012, proces można zastosować do modułu Human Resources: [Eksportowanie hierarchii stanowisk do programu Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).

Wykonaj następujące kroki, aby wyeksportować do programu Visio.

1. W module Human Resources otwórz stronę listy **Stanowiska**.

    Aby dołączyć więcej informacji w diagramie struktury organizacji, dodaj pola do listy **Stanowiska**, aby były one dostępne podczas korzystania z kreatora w dalszej części tej procedury.

2. W okienku akcji naciśnij przycisk **Otwórz w programie Microsoft Office**, a następnie, w obszarze **Eksportuj do programu Excel**, wybierz opcję **Stanowiska**. Alternatywnie naciśnij klawisze Ctrl + T.

    ![Eksportowanie strony listy Stanowiska do programu Excel](media/org-admin.png)

3. Zapisz plik programu Excel, który został wyeksportowany.

    ![Okno dialogowe Eksportuj do programu Excel](media/export-excel.png)

4. W programie Visio zaznacz **Visio — Utwórz nowy** i wybierz kategorię szablonu **Służbowy**.

    ![Nowy diagram](media/new.png)

5. Wybierz **Kreatora schematów organizacyjnych**, a następnie wybierz opcję **Utwórz**.

    ![Okno dialogowe Kreator schematów organizacji](media/orgchart-wizard.png)

6. Wybierz **Informacje, które już są przechowywane w pliku lub bazie danych**, a następnie wybierz opcję **Dalej**.

    ![Kreator schematów organizacyjnych 1](media/orgchart-wizard7.png)

7. Wybierz **Tekst, Org Plus (\*.txt) lub plik programu Excel**, a następnie wybierz opcję **Dalej**.

    ![Kreator schematów organizacyjnych 2](media/orgchart-wizard3.png)

8. Przeglądaj, aby wybrać wyeksportowany plik programu Excel zawierający hierarchię stanowisk, a następnie wybierz opcję **Dalej**.

    ![Kreator schematów organizacyjnych 3](media/orgchart-wizard2.png)

9. Ustaw pole **Nazwa** jako **Stanowisko**, ustaw pole **Podlega** jako **Stanowisko zwierzchnie**, a następnie wybierz **Dalej**.

    ![Kreator schematów organizacyjnych 4](media/orgchart-wizard1.png)

10. Wybierz pola, które mają być pokazywane na każdym węźle, a następnie wybierz opcję **Dalej**.

    ![Kreator schematów organizacyjnych 5](media/orgchart-wizard5.png)

11. Dodaj kolumnę **Stanowisko** do listy **pól danych kształtów**, a następnie wybierz **Dalej**.

    ![Kreator schematów organizacyjnych 6](media/orgchart-wizard6.png)

12. Obrazy nie są obecnie dostępne. W związku z tym, na następnej stronie wybierz **Dalej**.
13. Wybierz **Chcę użyć kreatora do automatycznego podzielenia schematu organizacyjnego na strony**.

    ![Kreator schematów organizacyjnych 7](media/orgchart-wizard4.png)

14. Wybierz **Zakończ**.

    Jeśli ma żadnych stanowisk, które nie znajdują się w strukturze, użytkownik jest proszony o uwzględnienie ich na diagramie.

Diagram, który jest generowany w programie Visio, zawiera każdego kierownika w oddzielnym arkuszu.

Na podstawie pól wybranych do uwzględnienia w schemacie, każdy węzeł wyświetla odpowiednie informacje podczas generowania pliku programu Visio.

![Diagram hierarchii](media/hierarchy.png)

**Opcja dodatkowa**

W programie Human Resources również można używać obszaru roboczego **Osoby** w celu wyświetlenia niektórych informacji dotyczących hierarchii.


[!INCLUDE[footer-include](../includes/footer-banner.md)]