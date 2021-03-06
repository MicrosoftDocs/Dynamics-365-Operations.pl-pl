---
title: Omówienie migawek (wersja zapoznawcza)
description: W tym temacie opisano funkcję migawek, która umożliwia zapisanie prognozy przepływów pieniężnych na potrzeby analizy lub porównania z wartościami rzeczywistymi w późniejszym czasie. Podczas generowania prognozy przepływów pieniężnych można zapisać tę prognozę jako „migawkę”. Następnie można używać migawek w celu edytowania kont uwzględnionych w prognozie lub porównywania prognozy w migawce z wartościami rzeczywistymi.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 593d6fa8efdecf1b64ef802e6861783d6f85489c
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186597"
---
# <a name="snapshots-overview-preview"></a>Omówienie migawek (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Migawki umożliwiają organizacjom edytowanie i zapisywanie informacji o ich stanie środków pieniężnych i prognozach kasowych w danym momencie. Migawkę można porównać z rzeczywistymi informacjami finansowymi, sprawdzić odchylenia, a następnie używać tych informacji do poprawiania prognoz przepływów pieniężnych w kolejnych okresach. W szczególności migawki mogą być używane w następujący sposób:

- Śledzenie stanu środków pieniężnych i prognoz kasowych.
- Filtrowanie danych w celu wyświetlenia podzbioru osób prawnych, dla których utworzono migawkę.
- Edytowanie stanu środków pieniężnych i prognozy kasowej wygenerowanych przez system.
- Przeprowadzanie analizy warunkowej dla optymistycznych, pesymistycznych i najbardziej prawdopodobnych przewidywań przepływów pieniężnych.
- Porównywanie rzeczywistych efektów finansowych z prognozą zapisaną w migawce.

Migawkę można utworzyć, wybierając opcję **Nowa migawka** na karcie **Stan środków pieniężnych** lub karcie **Prognoza kasowa** w obszarze roboczym **Prognozy przepływów pieniężnych**. Po utworzeniu migawki można edytować i zapisywać jej wpływy i rozchody gotówkowe. Wszystkie zapisane migawki są dostępne na karcie **Migawki** . Aby otworzyć migawkę, zaznacz jej nazwę.

Wpływy i rozchody gotówkowe w migawkach można w każdej chwili edytować. Po zmodyfikowaniu wpływu lub rozchodu gotówkowego zaktualizowana kwota jest dopisywana proporcjonalnie do kont płynności tworzących pierwotne saldo. Po zakończeniu edytowania migawki kliknij opcję **Zapisz**, aby zapisać wprowadzone zmiany.

Aby porównać wiele migawek, wybierz opcję **Porównaj migawki**. Można porównywać dwie migawki naraz. Zaznacz dwie migawki do porównania, a następnie kliknij przycisk **OK**. Na stronie **Porównanie migawek** zostanie wyświetlane porównania wybranych migawek. Wykres w górnej części strony pokazuje porównanie wpływów gotówkowych, rozchodów gotówkowych i sald bankowych w nakładających się okresach między dwiema migawkami. Siatka w dolnej części pokazuje szczegółowe porównanie dwóch prognoz dla każdej kwoty płynności. Kolumna **Odchylenie** w siatce pokazuje różnicę między saldami w okresie.

Aby porównać rzeczywiste wyniki finansowe z prognozą zapisaną jako migawka, wybierz opcję **Porównaj z wartościami rzeczywistymi**. Na stronie **Porównanie migawek** zostanie wyświetlone porównanie kwot rzeczywistych z prognozą. Wykres w górnej części strony pokazuje porównanie wpływów gotówkowych, rozchodów gotówkowych i sald bankowych w nakładających się okresach między dwiema migawkami. Siatka w dolnej części pokazuje szczegółowe porównanie sald wartości rzeczywistych z podziałem na okresy z prognozowanym saldem dla każdej kwoty płynności. Kolumna **Odchylenie** w siatce pokazuje różnicę między rzeczywistym saldem w okresie a prognozowanym saldem.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
