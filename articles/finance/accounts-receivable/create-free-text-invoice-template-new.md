---
title: Tworzenie szablonu faktury niezależnej
description: W tej procedurze przedstawiono tworzenie szablonu faktury niezależnej.
author: ShivamPandey-msft
ms.date: 05/29/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f84345aa8b157c5ca2a3025d4817af1fb1b1b2d009b3213d15a5b3daca8d763
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763269"
---
# <a name="create-a-free-text-invoice-template"></a>Tworzenie szablonu faktury niezależnej

[!include [banner](../includes/banner.md)]

Ten przewodnik wykorzystuje firmę demonstracyjną USMF. Ta procedura jest przeznaczona dla użytkownika, który odpowiada za zarządzanie i przetwarzanie faktur dla odbiorców.

## <a name="create-a-template"></a>Utwórz szablon

1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Faktury cykliczne > Szablon faktury niezależnej.
    * Ten formularz służy do tworzenia szablonów faktur niezależnych, które mogą zawierać wiersze faktur, opłaty, szablon zasad podziału księgowań oraz informacje o koncie księgowym.  
2. Kliknij przycisk „Nowy”, aby utworzyć nowy szablon faktury niezależnej.
3. W polu Nazwa szablonu wpisz wartość.
    * Pole „Nazwa szablonu” w sposób unikatowy identyfikuje szablon faktury niezależnej. Żadne dwa szablony nie mogą mieć takiej samej wartości „Nazwa szablonu”.  
4. W polu Opis wprowadź opis szablonu.
5. Rozwiń kartę Wiersze faktury.
6. W polu Opis wprowadź opis wiersza faktury.
7. W polu Konto główne wybierz konto przychodów.
    * Na stronie Profile księgowania odbiorców można wybrać konto transakcji przeciwstawnej dla księgowania łącznej kwoty faktury po stronie kredytowej odbiorcy.  
8. W polu Grupa podatków kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Grupa podatków dla bieżącego wiersza faktury jest domyślną grupą podatków dla konta odbiorcy.  
9. Na liście kliknij łącze w wybranym wierszu.
10. W polu Grupa podatków dla towaru wybierz grupę podatków od towaru dla bieżącego wiersza faktury.
11. Na liście kliknij łącze w wybranym wierszu.
12. W polu Cena jednostkowa wpisz lub wyświetl cenę za jednostkę towaru w wierszu faktury.
    * Ta kwota jest mnożona przez wartość w polu Ilość w celu ustalenia kwoty wiersza faktury.  
13. Dodaj nowy wiersz do szablonu faktury niezależnej.
14. W polu Opis wprowadź opis wiersza faktury.
15. W polu Konto główne wybierz konto przychodów.
    * Na stronie Profile księgowania odbiorców można wybrać konto transakcji przeciwstawnej dla księgowania łącznej kwoty faktury po stronie kredytowej odbiorcy.  
16. W polu Grupa podatków kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Grupa podatków dla bieżącego wiersza faktury jest domyślną grupą podatków dla konta odbiorcy.  
17. Na liście kliknij łącze w wybranym wierszu.
18. W polu Grupa podatków dla towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Grupa podatków dla towaru dla bieżącego wiersza faktury.  
19. Na liście kliknij łącze w wybranym wierszu.
20. Wprowadź lub wyświetl liczbę jednostek w wierszu faktury.
    * Ta liczba jest mnożona przez wartość w polu Cena jednostkowa w celu ustalenia kwoty wiersza faktury.  
21. Wprowadź lub wyświetl cenę jednostkową dla wiersza faktury. 
    * Ta kwota jest mnożona przez wartość w polu Ilość w celu ustalenia kwoty wiersza faktury.  
22. Wyświetl i zmodyfikuj zasady podziału księgowań dla określonego wiersza i jego wierszy podrzędnych.
    * Zasady podziału księgowań określają sposób księgowania kwot, czyli przychodów, podatków lub opłat, na fakturze niezależnej.  
23. Zaktualizuj zasady podziału księgowań dla wybranego wiersza faktury.
24. Kliknij przycisk Zamknij.

## <a name="save-a-free-text-invoice-as-a-template"></a>Zapisywanie faktury niezależnej jako szablonu
Istniejącą fakturę niezależną można również zapisać jako szablon. Gdy na karcie Faktura wybierzesz opcję Zapisz do szablonu, wprowadź nazwę i opis szablonu. Jeśli szablon o tej nazwie już istnieje, zobaczysz o tym powiadomienie. Nadal można kliknąć przycisk OK, aby zastąpić istniejący szablon. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]