---
title: Ustawienia zapotrzebowania
description: Ten temat zawiera informacje o ustawieniach zapotrzebowania, których planowanie główne używa do obliczania zapotrzebowania na towar.
author: t-benebo
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard, ReqItemTableSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e98f1ab83e27e36400cd312ef2af8554d22ea505
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470045"
---
# <a name="coverage-settings"></a>Ustawienia zapotrzebowania

[!include [banner](../includes/banner.md)]

Ustawienia zapotrzebowania są używane przez planowanie główne do obliczania zapotrzebowań na towary.

Ustawienia zapotrzebowania można określić na kilka sposobów:

- Określ ustawienia zapotrzebowania dla grupy zapotrzebowania.

    Można utworzyć grupę zapotrzebowania zawierająca ustawienia dotyczące wszystkich produktów połączonych z tą grupą zapotrzebowania. Aby utworzyć grupę zapotrzebowania, kliknij kolejno opcje **Planowanie główne &gt; Ustawienia &gt; Zapotrzebowanie &gt; Grupy zapotrzebowania**. Grupę zapotrzebowania można połączyć z produktem. Jeśli łącze jest właściwe dla oddziału, magazynu lub wymiaru produktu, użyj pola **grupa zapotrzebowania** na stronie **zapotrzebowanie na towar**. Jeśli łącze ma charakter ogólny, bez względu na wymiary produktu, należy użyć **grupy zapotrzebowania** na skróconej karcie **Plan** na stronie **Szczegóły produktu**. Domyślnie, jeśli grupa zapotrzebowania nie jest połączona z produktem, planowanie główne używa ogólnej grupy zapotrzebowania określonej na stronie **Parametry planowania głównego**.

- Określ ustawienia zapotrzebowania dla produktu.

    Ustawienia zapotrzebowania można utworzyć dla określonego produktu. Przejdź do **Zarządzanie informacjami o produktach&gt; Produkty &gt; Zwolnione produkty**. Wybierz produkt, a następnie w okienku akcji na karcie **Plan** w obszarze **Grupa zapotrzebowania** wybierz **Zapotrzebowanie na towar**, aby otworzyć stronę **Zapotrzebowanie na towar**. Jeśli produkt jest połączony z grupą zapotrzebowania, ustawienia grupy zapotrzebowania można zastąpić, korzystając z pola **Zastąp**. Ustawienia zapotrzebowania na stronie **Zapotrzebowanie na towar** mają pierwszeństwo przed ustawieniami na stronie **Grupa zapotrzebowania**.

- Określ ustawienia zapotrzebowania dla produktu za pomocą kreatora.

    Kreator przeprowadzi Cię krok po kroku przez proces konfigurowania podstawowych parametrów zapotrzebowania na towar. Na stronie **Zapotrzebowanie na towar** w okienku akcji kliknij **Kreator**, aby otworzyć **Kreator zapotrzebowania na towar**.

- Określ ustawienia zapotrzebowania dla grupy wymiarów.

    Przejdź do **Zarządzanie informacjami o produktach&gt; Produkty &gt; Zwolnione produkty**. Na stronie **Szczegóły zwolnionego produktu** na skróconej karcie **Ogólne** w grupie **Administracja** kliknij łącze w polu **Grupa wymiarów magazynowania**. Na stronie **Grupy wymiarów magazynowania** zaznacz pole **Plan zapotrzebowania wg wymiaru**, aby utworzyć ustawienia zapotrzebowania dla wymiaru w grupie wymiarów magazynowania. Wszystkie wymiary produktów, takie jak konfiguracja, kolor, rozmiar, styl, muszą mieć zaznaczone pole **Plan zapotrzebowania wg wymiaru**.


## <a name="coverage-codes"></a>Kody zapotrzebowania

Planowanie główne można skonfigurować w taki sposób, aby korzystało z różnych metod uzupełniania zapasów. Metody uzupełniania lub metody ustalania wielkości zapasów są technikami stosowanymi w systemie do określania rozmiaru partii zakupionych lub wyprodukowanych towarów. 

Do każdej metody uzupełnień jest przypisany jeden z następujących kodów zapotrzebowania:

- **Ręczna** — metoda ustalania rozmiaru partii, w której system nie sugeruje nabywania, przenoszenia lub zleceń produkcyjnych dla danego towaru. Terminarz pozycji będzie odpowiedzialny za tworzenie wymaganych zamówień uzupełniania towaru.
- **Dla zapotrzebowania** — metoda ustalania rozmiaru partii, w której system tworzy planowany zakup, przeniesienie lub zlecenie produkcyjne według zapotrzebowania na dany towar. Jest to zwykle używane w przypadku kosztownych towarów ze sporadycznym popytem.  
- **Na okres** — metoda określania rozmiaru partii, która łączy wszystkie zapotrzebowania na okres w jednym zamówieniu towaru. Zamówienie zostanie zaplanowane na pierwszy dzień okresu, a jego ilość będzie spełniać zapotrzebowania netto w ustalonym okresie. Okres rozpoczyna się od pierwszego zapotrzebowania na towar i obejmuje zdefiniowany okres w czasie. Następny okres rozpocznie się od kolejnych wymagań dotyczących towaru.
- **Minimum/maksimum** — metoda określania rozmiaru partii, która zawiera uzupełnienie zapasów do określonego poziomu, gdy przewidywana ilość zapasów jest mniejsza niż wartość progowa. Ilość uzupełniania zapasów będzie różnicą między maksymalnym poziomem i przewidywanym poziomem zapasów.


## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie planów głównych](master-plans.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]