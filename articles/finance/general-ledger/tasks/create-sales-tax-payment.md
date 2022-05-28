---
title: Tworzenie płatności podatku
description: Procedura zadania rozliczenia i księgowania podatku rozlicza salda podatku na kontach podatków i kompensuje je na koncie rozliczeniowym podatku za dany okres.
author: twheeloc
ms.date: 01/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c388a8f98cd4581abe2ec13d8922e232321e4039
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735939"
---
# <a name="create-a-sales-tax-payment"></a>Tworzenie płatności podatku

[!include [banner](../../includes/banner.md)]

Procedura zadania rozliczenia i księgowania podatku rozlicza salda podatku na kontach podatków i kompensuje je na koncie rozliczeniowym podatku za dany okres.

1. Wybierz kolejno opcje **Podatek > Deklaracje > Podatek > Rozlicz i zaksięguj podatek**.
2. W polu **Okres rozliczeniowy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście kliknij łącze w wybranym wierszu.
4. W polu **Od dnia** wprowadź datę. Jeśli na stronie **Parametry księgi głównej** nie zaznaczono opcji **Uwzględnij korekty**, rozliczenie może być przetwarzane dla różnych wersji. **Oryginał** jest pierwszym rozliczeniem w interwale okresu i może być przetwarzany tylko raz w interwale. Najnowsze korekty rozliczają transakcje podatkowe, które zostały zaksięgowane po utworzeniu oryginalnej wersji.
5. W polu **Data transakcji** wprowadź datę.
6. Kliknij przycisk **OK**. Raport **Płatności podatku** jest drukowany w celu przejrzenia rozliczonych transakcji podatkowych w okresie.

Począwszy od wersji Finance 10.0.24, możesz pominąć **Płatności podatku od sprzedaży** raport generowany zaraz po wdrożeniu procedury okresowej **Rozlicz i księguj podatek** w ramach **Oddzielne generowanie raportu płatności podatku z rozliczenia podatku obrotowego** w obszarze roboczym **Zarządzanie funkcjami**.

Jeśli ta funkcja jest włączona, po zakończeniu procesu rozliczania nie jest drukowany raport płatności podatku. Zamiast tego jest wyświetlany następujący komunikat: „Rozliczanie i księgowanie podatku od sprzedaży zostało zakończone. Załącznik „xxxx, m/d/rrrr” został wysłany."

Nadal możesz ręcznie wygenerować raport dotyczący podatku od sprzedaży, przechodząc do **Podatek** > **Zapytania i raporty** > **Zapytania dotyczące podatków** > **Płatności podatków**.

## <a name="performance-consideration"></a>Zagadnienia dotyczące wydajności

Procedura płatności podatku może zająć dużo czasu. Główne czynniki wpływające na wydajność procedury to liczba faktur w okresie rozliczeniowym oraz liczba wpisów, które muszą zostać zaksięgowane w załączniku rozliczenia podatku. Aby poprawić wydajność, można wybrać opcję pomijania niektórych funkcji, które nie są wymagane w procesie.

### <a name="enable-the-sales-tax-payment-performance-improvement-feature"></a>Włączanie funkcji poprawy wydajności płatności podatku

Funkcja **poprawy wydajności płatności podatku** może pomóc zwiększyć wydajność procedury płatności podatku przez zsumowanie kwoty w walucie rozliczeniowej i kwoty w walucie raportowania w wierszach załącznika płatności podatku, które mają takie same konto główne, wymiar księgowy i walutę.

1. Wybierz kolejno opcje **Administrator systemu** \> **Obszary robocze** \> **Zarządzanie funkcjami**.
2. Na karcie **Wszystkie** wyszukaj i wybierz opcję **poprawy wydajności płatności podatku**.
3. Wybierz **Włącz**.

### <a name="prevent-generation-of-offset-tax-transactions"></a>Zapobieganie generowaniu przeciwstawnych transakcji podatkowych

Domyślnie załącznik płatności podatku służy do księgowania przeciwstawnych transakcji podatkowych względem każdej transakcji podatkowej rozliczanej w ramach procedury płatności podatku. Te przeciwstawne transakcje podatku są uwzględniane w raporcie **uzgadniania podatku/księgi**. Pokazują one zaległe saldo transakcji podatkowych, które nie zostały rozliczone w danym okresie.

Jednak przeciwstawne transakcje podatku mogą zwiększyć obciążenie procedury płatności podatku. W związku z tym na żądanie można aktywować dystrybucję o nazwie **TaxReportGenOffsetTaxTransPerRecordSetFlighting**. Ta dystrybucja testowa może poprawić wydajność generowania transakcji przeciwstawnych podatków dla krajów i regionów z wyjątkiem Tajlandii, Polski, Węgier, Litwy, Malezji, Indii, Włoch, Rosji, Czech, Estonii i Łotwy.

> [!NOTE]
> Jeśli w tabeli transakcji podatkowych znajdują się pola dostosowane, nie można aktywować dystrybucji testowej.

Ponieważ raport **uzgodnienia podatku/księgi** jest na ogół używany tylko do celów kontroli wewnętrznej i nie jest wymagany w wielu systemach podatkowych, można nie generować przeciwstawnych transakcji podatkowych w załączniku płatności podatku.

1. Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Okresy rozliczania podatku**.
2. Wybierz okres rozliczeniowy.
3. Na skróconej karcie **Ogólne** ustaw opcję **Zapobiegaj generowaniu transakcji podatków przeciwstawnych** na **Tak**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
