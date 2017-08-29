--- 
title: "Tworzenie i przetwarzanie zgodności"
description: "Ta procedura służy do zarządzania niezgodnościami na podstawie istniejącego zlecenia kontroli jakości."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 4082caf2cc8393345d4f79a991f2cf205b06b142
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-process-a-conformance"></a>Tworzenie i przetwarzanie zgodności

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura służy do zarządzania niezgodnościami na podstawie istniejącego zlecenia kontroli jakości. To nagranie można uruchomić w kontekście firmy demonstracyjnej USMF i użyć sugerowanych wartości. Zazwyczaj ta procedura jest wykonywana przez pracownika ds. kontroli jakości.  Warunkiem wstępnym jest przejście nagrania zadania „Sprawdzenie jakości towarów”. Aby wykonać zatwierdzenie niezgodności, użytkownik, który uruchomił nagranie zadania, musi mieć przypisaną wartość „Nazwa” na stronie Użytkownicy. Aby korzystać z notatek do dokumentu, użytkownik musi mieć również włączoną funkcję Obsługa dokumentu w opcjach użytkownika. 


## <a name="select-a-quality-order"></a>Wybieranie zlecenia kontroli jakości
1. Przejdź do okna Zlecenia kontroli jakości.
2. Na liście oznacz wybrany wiersz.
    * Wybierz zlecenie kontroli jakości utworzone w nagraniu zadania „Sprawdzenie jakości towarów”.  

## <a name="create-a-nonconformance"></a>Tworzenie rekordu niezgodności
1. Kliknij przycisk Informacje.
2. Kliknij opcję Niezgodności.
3. Kliknij przycisk Nowy.
4. W polu Typ problemu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wybierz problem, który został znaleziony podczas procesu inspekcji.  
5. W polu Typ problemu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. Kliknij przycisk OK.

## <a name="approvereject-a-nonconformance"></a>Zatwierdzanie/odrzucanie rekordu niezgodności
1. Kliknij przycisk Funkcje.
2. Kliknij opcję Zatwierdź niezgodność.
    * W tym przykładzie zatwierdź niezgodność. Zatwierdzone niezgodności można skojarzyć z powiązanymi operacjami w celu zarejestrowania pracy wykonywanej w ramach postępowania z niezgodnością oraz, tak jak w tym nagraniu zadanie, w ramach przetwarzania korekty.  
3. Kliknij przycisk Tak.

## <a name="create-a-correction-action"></a>Tworzenie działania naprawczego
1. Kliknij opcję Korekty.
2. Kliknij przycisk Nowy.
3. Na liście oznacz wybrany wiersz.
4. W polu Numer pracownika kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście kliknij łącze w wybranym wierszu.
6. Kliknij opcję Wybierz.
7. Kliknij opcję Dołącz.
    * Utwórz notatkę dotyczącą korekty. W tym przykładzie działanie polega na skontaktowaniu się z dostawcą w celu omówienia przypadku niezgodności.  
8. Kliknij przycisk Nowy.
9. Kliknij opcję Notatka.
    * Należy zauważyć, że w zależności od konfiguracji raportu mogą być drukowane różne typy dokumentów towarzyszących, które są związane z zarządzaniem niezgodnościami.  
10. Wypełnij pole Opis.
11. Zamknij stronę.

## <a name="maintain-a-correction"></a>Obsługa korekty
1. Kliknij opcję Oznacz jako ukończone.
2. Kliknij przycisk OK.
3. Zamknij stronę.

## <a name="close-a-nonconformance"></a>Zamykanie rekordu niezgodności
1. Kliknij przycisk Funkcje.
2. Kliknij opcję Zamknij niezgodność.
3. Kliknij przycisk Tak.
4. Zamknij stronę.
5. Zamknij stronę.


