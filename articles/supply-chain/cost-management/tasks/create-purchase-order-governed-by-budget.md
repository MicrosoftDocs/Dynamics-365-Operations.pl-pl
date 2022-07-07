---
title: Tworzenie zamówienia zakupu regulowanego budżetem
description: Ta procedura służy do tworzenia zamówienia zakupu sprawdzanego pod kątem dostępnego budżetu.
author: JennySong-SH
ms.date: 06/15/2020
ms.topic: business-process
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa9777ad3aa487dfb558879335f93f347b8ac749
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016196"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>Tworzenie zamówienia zakupu regulowanego budżetem

[!include [banner](../../includes/banner.md)]

Ta procedura służy do tworzenia zamówienia zakupu sprawdzanego pod kątem dostępnego budżetu.

## <a name="review-the-budget-control-configuration"></a>Przeglądanie konfiguracji kontroli budżetu

1. Wybierz kolejno opcje **Budżetowanie > Ustawienia > Kontrola budżetu > Konfiguracja kontroli budżetu**.
1. Wybierz kartę **Dostępne środki budżetowe**.
1. Wybierz kartę **Dokumenty i arkusze**.
1. Wybierz kartę **Definiowanie reguł kontroli budżetu**.
1. Wybierz kartę **Zdefiniuj grupy budżetu**.
1. Zamknij stronę.

## <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu**.
1. Wybierz pozycję **Nowy**.
1. W polu **Konto dostawcy** wprowadź lub wybierz wartość.
1. Rozwiń skróconą kartę **Ogólne**.
1. W polu **Data księgowania** i ustaw datę.
1. Wybierz przycisk **OK**, aby zamknąć okno dialogowe i otworzyć nowe zamówienie zakupu.
1. Na skróconej karcie **Wiersze zamówienia zakupu** wybierz pozycję **Dodaj wiersz** na pasku narzędzi, aby dodać nowy wiersz, a następnie w razie potrzeby wypełnij wiersz, aby dodać towar do zamówienia.
1. Na pasku narzędzie skróconej karty **Wiersze zamówienia zakupu** wybierz **Finanse \> Dystrybuuj kwoty**.
1. W polu **Konto księgi** określ konto.
1. Zamknij stronę.

## <a name="perform-budget-checking"></a>Wykonaj kontrolę budżetu

1. Kontynuuj pracę z zamówieniem zakupu, do którego właśnie dodano wiersz.
1. Na pasku narzędzie skróconej karty **Wiersze zamówienia zakupu** wybierz **Finanse \> Przeprowadź sprawdzenie budżetu**.
1. Na pasku narzędzie skróconej karty **Wiersze zamówienia zakupu** wybierz **Finanse \> Błędy i ostrzeżenia sprawdzania budżetu**.
1. Otworzy się okno dialogowe **Błędy i ostrzeżenia sprawdzania budżetu**. Sprawdź wyniki sprawdzenia, a następnie wybierz przycisk **Zamknij**, aby zamknąć okno dialogowe.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]