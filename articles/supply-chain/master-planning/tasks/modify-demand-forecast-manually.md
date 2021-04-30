---
title: Ręczne modyfikowanie prognozy popytu
description: W tym temacie opisano, jak zmodyfikować prognozę dla towaru
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5da1d5b1fbd91964e695a704681b1c9ee513a2f1
ms.sourcegitcommit: 4016c223a985c46e33f9941bf91ba5e1583e1cfd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889031"
---
# <a name="modify-a-demand-forecast-manually"></a>Ręczne modyfikowanie prognozy popytu

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób modyfikowania prognozy dla towaru. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Ta procedura jest przeznaczona dla planisty produkcji.

## <a name="modify-the-forecast-for-a-selected-item"></a>Modyfikowanie prognozy na wybrany towar

Aby zmodyfikować prognozę dla wybranego elementu:

1. Przejdź do **Moduły \> Zarządzanie informacjami o produkcie \> Produkty \> Zwolnione produkty**.
1. Na liście znajdź i zaznacz odpowiedni rekord. Wybierz towar, dla którego chcesz zmodyfikować prognozę.
1. W okienku akcji otwórz kartę **Plan** i wybierz pozycję **Prognoza popytu**.
1. Na liście zaznacz wiersz. Jeśli nie ma żadnych wierszy prognozy, utwórz nowy wiersz przez wybranie przycisku **Nowy** w okienku akcji.  
1. W polu **Ilość sprzedaży** wprowadź liczbę dodatnią. Ta liczba reprezentuje prognozowaną ilość towaru. W przypadku wprowadzenia liczby ujemnej wyświetlany jest błąd.
1. W razie potrzeby wypełnij pola.
1. W okienku akcji wybierz opcję **Zapisz**.

## <a name="modify-the-forecast-for-one-or-more-items-microsoft-excel"></a>Modyfikowanie prognozy dla jednego lub większej liczby towarów Microsoft Excel

Aby zmodyfikować prognozę dla jednego lub więcej towarów Microsoft Excel:

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
