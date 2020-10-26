---
title: Rejestrowanie elementów dla zaawansowanego magazynowania za pomocą arkusza przyjęć towarów
description: W tej procedurze pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używany zaawansowany proces zarządzania magazynem.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea8b5e03282aa21aa9dfa486b1deaced6af4601c
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976931"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a>Rejestrowanie elementów dla zaawansowanego magazynowania za pomocą arkusza przyjęć towarów

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używany zaawansowany proces zarządzania magazynem. Zazwyczaj wykonuje to pracownik przyjmujący. 

Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Przed rozpoczęciem wykonywania zadań z przewodnika musisz mieć potwierdzone zamówienie zakupu z otwartym wierszem zamówienia zakupu. Towar w wierszu musi być magazynowy, nie może używać wariantów produktu i nie może mieć wymiarów śledzenia. Towar musi być także skojarzony z grupą wymiarów magazynowania, która obsługuje proces zarządzania magazynem. Używany magazyn musi mieć włączoną obsługę procesów zarządzania magazynem, a lokalizacji używana dla przyjęć musi być kontrolowana przez numer identyfikacyjny. Jeśli używasz firmy USMF, można użyć firmy 1001, magazynu 51 i towaru M9200, aby utworzyć zamówienie zakupu. 

Zapisz numer tworzonego zamówienia zakupu, a także numer towaru i oddział użyte w wierszu zamówienia zakupu.


## <a name="create-an-item-arrival-journal-header"></a>Tworzenie nagłówka arkusza przyjęcia towaru
1. Przejdź do okna Przyjęcie towaru.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
    * Jeśli używasz firmy USMF, możesz wpisać WHS. Jeśli korzystasz z innych danych, to arkusz, którego nazwę wybierzesz, musi mieć następujące właściwości: w polu Sprawdzanie lokalizacji pobrania ustawiona wartość Nie oraz w polu Zarządzanie kwarantanną ustawiona wartość Nie.  
4. W polu Numer wpisz wartość.
5. W polu Oddział wpisz wartość.
    * Wybierz oddział, który został użyty w wierszu zamówienia zakupu. Będzie on służył jako wartość domyślna ustawiana we wszystkich wierszach w arkuszu. Jeśli użyto magazynu 51 z firmy USMF, wybierz oddział 5.  
6. W polu Magazyn wpisz wartość.
    * Wybierz prawidłowy magazyn dla wybranego oddziału. Będzie on służył jako wartość domyślna ustawiana we wszystkich wierszach w arkuszu. Jeśli używasz przykładowych wartości z firmy USMF, wybierz magazyn 51.  
7. W polu Lokalizacja wpisz wartość.
    * Wybierz prawidłową lokalizację w wybranym magazynie. Lokalizacja musi być skojarzona z profilem lokalizacji, który jest kontrolowany przez numer identyfikacyjny. Będzie on służył jako wartość domyślna ustawiana we wszystkich wierszach w arkuszu. Jeśli używasz przykładowych wartości z firmy USMF, wybierz lokalizację Bulk-008.  
8. Kliknij prawym przyciskiem myszy strzałkę rozwijaną w polu Numer identyfikacyjny i wybierz polecenie Wyświetl szczegóły.
9. Kliknij przycisk Nowy.
10. W polu Numer identyfikacyjny wpisz wartość.
    * Zanotuj wartość.  
11. Kliknij przycisk Zapisz.
12. Zamknij stronę.
13. W polu Numer identyfikacyjny wpisz wartość.
    * Wprowadź wartość utworzonego właśnie numeru identyfikacyjnego. Będzie on służył jako wartość domyślna ustawiana we wszystkich wierszach w arkuszu.  
14. Kliknij przycisk OK.

## <a name="add-a-line"></a>Dodawanie wiersza
1. Kliknij przycisk Dodaj wiersz.
2. W polu Numer towaru wpisz wartość.
    * Wprowadź numer towaru użyty w wierszu zamówienia zakupu.  
3. Wprowadź liczbę w polu Ilość.
    * Wprowadź ilość, jaką chcesz zarejestrować.  
    * Pole Data określa dzień, kiedy dostępna ilość tego towaru zostanie zarejestrowana w magazynie.  
    * Pole Identyfikator partii zostanie wypełnione przez system, jeśli można je unikatowo zidentyfikować na podstawie dostarczonych informacji. W przeciwnym razie należy go dodać ręcznie. To pole jest wymagane i łączy tę rejestrację z określonym wierszem dokumentu źródłowego.  

## <a name="complete-the-registration"></a>Rejestrowanie
1. Kliknij przycisk Sprawdź poprawność.
    * Spowoduje to sprawdzenie, czy arkusz jest gotowy do zaksięgowania. Jeżeli weryfikacja przyniesie wynik negatywny, trzeba naprawić błędy, zanim będzie można zaksięgować arkusz.  
2. Kliknij przycisk OK.
    * Po kliknięciu przycisku OK sprawdź pasek komunikatów. Powinien tam być komunikat z informacją, że arkusz jest poprawny.  
3. Kliknij przycisk Księguj.
4. Kliknij przycisk OK.
    * Po kliknięciu przycisku OK sprawdź pasek komunikatów. Powinien tam być komunikat z informacją, że operacja została wykonana.  
5. Zamknij stronę.

