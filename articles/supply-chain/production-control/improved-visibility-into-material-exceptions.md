---
title: Uzyskiwanie wglądu w wyjątki dotyczące materiałów
description: W tym artykule opisano, jak uzyskać lepszy wgląd w wyjątki dotyczące materiałów dla zleceń produkcyjnych i zamówień partii.
author: johanhoffmann
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, WHSProdWaveTableListPage, WHSProdWaveTableManageBOMPool
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: a7877743a9ebd98263bc5614c0015bf33d463832
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863832"
---
# <a name="visibility-into-material-exceptions"></a>Uzyskiwanie wglądu w wyjątki dotyczące materiałów

[!include [banner](../includes/banner.md)]

W obszarze roboczym **Zarządzanie halą produkcyjną** trzy kafelki zapewniają lepszy wgląd w wyjątki dotyczące surowców dla zleceń produkcyjnych i zamówień partii:

- Niezwolnione wiersze dla materiałów wymagające uwagi
- Nieprzetworzone grupy czynności wymagające uwagi
- Otwarta praca magazynowa wymagająca uwagi

Dla wszystkich trzech kafelków data surowców wierszy listy składowej (BOM) i wierszy formuły jest porównywana z datą obszaru roboczego, a także filtrami parametrów **Jednostka produkcyjna**, **Grupa zasobów** i **Zasób** ustawionych w menu **Konfiguruj mój obszar roboczy**. Domyślnie data obszaru roboczego jest ustawiona na bieżącą datę, ale można ją dostosować.

Niepublikowany wiersz BOM lub wiersz formuły wymaga uwagi, jeżeli data surowca wiersza jest taka sama lub wcześniejsza niż data obszaru roboczego i jeżeli spełnia kryteria zdefiniowane przez filtry w obszarze roboczym.

Na poniższym rysunku niebieski pasek oznacza zadanie produkcyjne zaplanowane w zasobie. Rozpoczęcie zadania zaplanowano na 1 maja 2017 r. (01/05/2017). Ta data jest datą surowca. Innymi słowy, materiały, które są przypisane do zadania w wierszach BOM muszą być gotowe w tym dniu. Druga data na rysunku, 6 maja 2017 r. (06/05/2017), oznacza datę obszaru roboczego. W tym przykładzie data surowca jest wcześniejsza niż data obszaru roboczego. Dlatego data rozpoczęcia zużywania surowca upłynęła, a wiersze BOM i formuły spełniają kryteria konieczności uwagi.

![Przykład zadania produkcyjnego, w którym data surowca jest wcześniejsza niż data obszaru roboczego.](./media/improved-visibility.png)

## <a name="unreleased-material-lines-needing-attention"></a>Niezwolnione wiersze dla materiałów wymagające uwagi

Wiersz BOM lub formuły można zwolnić do magazynu na trzy sposoby:

- W ramach zwalniania zlecenia produkcyjnego lub zamówienia partii
- Jako zwolnienie ręczne
- Automatycznie za pomocą zadania wsadowego

Aby uzyskać więcej informacji, zobacz [Zwalnianie wierszy BOM i wierszy formuły do magazynu](releasing-bom-and-formula-lines-to-warehouse.md). 

Jeżeli wiersz BOM lub wiersz formuły nie zostały zwolnione lub zostały zwolnione tylko częściowo, a kryteria filtra i daty obszaru roboczego są spełnione,, wiersz jest uwzględniany w obliczaniu wartości widocznej na kafelku **Niezwolnione wiersze dla materiałów wymagające uwagi**.

Po wybraniu kafelka zostanie otwarta strona **Zwolnij do magazynu**. Ta strona zawiera liczbę niezwolnionych wierszy BOM i wierszy formuły podaną na kafelku. Niezwolnione wiersze są widoczne w górnej siatce. Ta siatka przedstawia pierwotnie szacowaną ilość dla wiersza, ilość już zwolnioną i pozostałą ilość, która ma jeszcze zostać zwolniona. Wiersze można dodawać od górnej do dolnej siatki. Następnie można zwalniać wybrane wiersze do magazynu od dolnej siatki. Począwszy od dolnej siatki można także dostosować ilość do zwolnienia, aby zwolnić tylko częściową ilość.

## <a name="unprocessed-waves-needing-attention"></a>Nieprzetworzone grupy czynności wymagające uwagi

Po zwolnieniu wiersza BOM lub wiersza formuły jest on dodawany do nowej grupy czynności produkcji lub istniejącej otwartej grupy czynności, w zależności od konfiguracji szablonu grupy czynności produkcji. Za pomocą konfiguracji szablonu grupy czynności można także skonfigurować grupę czynności tak, aby była automatycznie przetwarzana po zwolnieniu wiersza BOM lub wiersza formuły. Podczas przetwarzania grupy czynności jest tworzona praca magazynowa dla pobrania surowców. Jeżeli szablon grupy czynności jest skonfigurowany tak, aby grupy czynności nie były przetwarzane w momencie zwolnienia, grupa czynności pozostaje w stanie nieprzetworzonym. Kafelek **Nieprzetworzone grupy czynności wymagające uwagi** zawiera liczbę wierszy BOM i wierszy formuły które zostały zwolnione do magazynu w nieprzetworzonych grupach czynności, i mające taką samą lub wcześniejszą datę surowca jako data obszaru roboczego. Wiersze muszą także zostać wykorzystane przez zasób operacji stosowany do filtra obszaru roboczego.

Po wybraniu kafelka otwierana jest strona **Wszystkie grupy czynności produkcji**. Ta strona jest filtrowana przez liczbę otwartych grup czynności zawierających wiersze grup czynności ze zwolnionych wierszy BOM i wierszy formuły spełniających kryteria kafelka.

### <a name="manually-maintain-production-waves"></a>Ręczna obsługa wszystkich procesów produkcyjnych

Na stronie **Wszystkie grupy czynności produkcji** można używać przycisków na karcie **Grupy czynności** w okienku akcji, aby ręcznie **Przetwarzać** i **Zwalniać** grupy czynności. Możesz również użyć opcji **Obsługa produkcji**, aby wyświetlić i obsługiwać dane **Puli BOM produkcji**, które są używane do obsługi procesu machania.

## <a name="open-warehouse-work-needing-attention"></a>Otwarta praca magazynowa wymagająca uwagi

Kafelek **Otwarta praca magazynowa wymagająca uwagi** zawiera liczbę wierszy BOM i wierszy formuły które zostały zwolnione do magazynu, mające nieprzetworzoną pracę i taką samą lub wcześniejszą datę surowca jako data obszaru roboczego. Wiersze muszą także zostać wykorzystane przez zasób operacji stosowany do filtra obszaru roboczego.

Po wybraniu kafelka otwierana jest strona **Cała praca**. Ta strona jest filtrowana przez liczbę otwartych nagłówków pracy zawierających wiersze pracy ze zwolnionych wierszy BOM i wierszy formuły spełniających kryteria kafelka. Na stronie **Cała praca** można ręcznie przetworzyć pracę.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]