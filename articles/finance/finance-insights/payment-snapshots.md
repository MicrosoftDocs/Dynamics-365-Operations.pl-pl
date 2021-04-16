---
title: Omówienie migawek (wersja zapoznawcza)
description: W tym temacie opisano funkcję migawek, która umożliwia zapisanie prognozy przepływów pieniężnych na potrzeby analizy lub porównania z wartościami rzeczywistymi w późniejszym czasie. Podczas generowania prognozy przepływów pieniężnych można zapisać tę prognozę jako „migawkę”. Następnie można używać migawek w celu edytowania kont uwzględnionych w prognozie lub porównywania prognozy w migawce z wartościami rzeczywistymi.
author: ShivamPandey-msft
ms.date: 05/19/2020
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
ms.openlocfilehash: 07854d47fa2e42ea0d49cde193a2040415acf089
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827249"
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

#### <a name="privacy-notice"></a>Klauzula prywatności
Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]