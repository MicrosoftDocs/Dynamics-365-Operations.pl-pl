---
title: 'Przewodnik: Ręczne modyfikowanie prognozy popytu'
description: W tym temacie opisano, jak zmodyfikować prognozę dla towaru
author: t-benebo
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e5030bf97bee8dc475f22473ecc87e900298b6f
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469414"
---
# <a name="guide-modify-a-demand-forecast-manually"></a>Przewodnik: Ręczne modyfikowanie prognozy popytu

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób modyfikowania prognozy dla towaru. Ta procedura jest przeznaczona dla planisty produkcji.

## <a name="modify-the-forecast-for-a-selected-item"></a>Modyfikowanie prognozy na wybrany towar

Aby zmodyfikować prognozę dla wybranego elementu:

1. Przejdź do **Moduły \> Zarządzanie informacjami o produkcie \> Produkty \> Zwolnione produkty**.
1. Na liście znajdź i zaznacz odpowiedni rekord. Wybierz towar, dla którego chcesz zmodyfikować prognozę.
1. W okienku akcji otwórz kartę **Plan** i wybierz pozycję **Prognoza popytu**.
1. Na liście zaznacz wiersz. Jeśli nie ma żadnych wierszy prognozy, utwórz nowy wiersz przez wybranie przycisku **Nowy** w okienku akcji.  
1. W polu **Ilość sprzedaży** wprowadź liczbę dodatnią. Ta liczba reprezentuje prognozowaną ilość towaru. W przypadku wprowadzenia liczby ujemnej wyświetlany jest błąd.
1. W razie potrzeby wypełnij pola.
1. W okienku akcji wybierz opcję **Zapisz**.

## <a name="modify-the-forecast-for-one-or-more-items-with-microsoft-excel"></a>Zmodyfikuj prognozę dla jednego lub więcej towarów za pomocą Microsoft Excel

Aby zmodyfikować prognozę dla jednego lub więcej towarów za pomocą Microsoft Excel:

1. Wykonaj jedną z następujących czynności:
    - Otwórz stronę **Prognozy popytu** dla dowolnej pozycji (niezależnie od tego, która z nich) została opisana w poprzedniej sekcji.
    - Wybierz kolejno opcje **Planowanie główne \> Prognozowanie \> Ręczne wprowadzanie prognozy \> Wiersze prognozy popytu**.
1. W okienku akcji wybierz **Otwórz w Microsoft Office \> Wpisy prognozy popytu**.
1. Wybierz lokalizację pobierania, zapisz, a następnie otwórz pobrany plik w programie Excel.
1. Jeśli zostanie wyświetlane ostrzeżenie, wybierz opcję **Włącz edytowanie**.
1. W programie Excel zaloguj się do Supply Chain Management przy użyciu okienka zadań Microsoft Dynamics. Musisz się zalogować, gdy włączona jest opcja **Nie wylogowuj mnie** i musisz ufać aplikacji do połączeń z danymi.
1. W arkuszu programu Excel są teraz wszystkie wiersze bieżącej prognozy popytu dla firmy.  W razie potrzeby dodawaj, usuwaj i edytuj wiersze prognozy popytu.
1. Wybierz opcję **Publikuj** w okienku zadań Microsoft Dynamics, aby przekazać zmiany z powrotem do Supply Chain Management.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
