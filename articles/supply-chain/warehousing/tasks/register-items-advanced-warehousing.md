---
title: Rejestrowanie pozycji włączonych dla procesów zarządzania magazynem za pomocą arkusza przyjęć towarów
description: W tym artykule pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używany zaawansowany proces zarządzania magazynem (WMS).
author: Mirzaab
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5241c982675d6b9a9bc9596b8ac9ed2798903287
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066976"
---
# <a name="register-items-enabled-for-warehouse-management-processes-using-an-item-arrival-journal"></a>Rejestrowanie pozycji włączonych dla procesów zarządzania magazynem za pomocą arkusza przyjęć towarów

[!include [banner](../../includes/banner.md)]

W tym artykule pokazano sposób rejestrowania towarów za pomocą arkusza przyjęcia towaru, gdy jest używany zaawansowany proces zarządzania magazynem (WMS). Zazwyczaj wykonuje to pracownik przyjmujący.

## <a name="enable-sample-data"></a>Włącz dane przykładowe

Aby przejść przez ten scenariusz, używając przykładowych rekordów i wartości określonych w tym artykule, musisz używać systemu, w którym są zainstalowane standardowe dane demonstracyjne, i przed rozpoczęciem musisz wybrać firmy *USMF*.

Zamiast tego można przejść przez ten scenariusz, zastępując wartości z własnych danych, pod warunkiem że dostępne są następujące dane:

- Musisz mieć potwierdzone zamówienie zakupu z otwartym wierszem zamówienia zakupu.
- Towar w wierszu musi być magazynowany. Nie może używać wariantów produktu i nie może mieć wymiarów śledzenia.
- Towar musi być skojarzony z grupą wymiarów magazynu, dla której jest włączony proces zarządzania magazynem.
- Używany magazyn musi mieć włączoną obsługę procesów WMS, a lokalizacji używana dla przyjęć musi być kontrolowana przez numer identyfikacyjny.

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a>Tworzenie nagłówka arkusza przybycia towaru, który korzysta z zarządzania magazynem

Poniższy scenariusz przedstawia sposób tworzenia nagłówka arkusza przybycia towaru, w którym jest używane zarządzanie magazynem:

1. Upewnij się, że system zawiera potwierdzone zamówienie zakupu spełniające wymagania opisane w poprzedniej sekcji. W tym scenariuszu jest używane zamówienie zakupu dla firmy *USMF*, konta dostawcy *1001*, magazynu *51*, z wierszem zamówienia dla *10 PL* (10 palet) numeru pozycji *M9200*.
1. Zanotuj numer zamówienia zakupu do użycia.
1. Wybierz kolejno opcje **Zarządzanie zapasami \> Wpisy w arkuszu \> Przyjęcie towaru \> Przyjęcie towaru**.
1. Wybierz pozycję **Nowy** w okienku akcji.
1. Zostanie otwarte okno dialogowe **Tworzenie arkusza zarządzania magazynem**. W polu **Nazwa** wybierz nazwę arkusza.
    - Jeśli używasz danych firmy demonstracyjnej *USMF*, wybierz opcję *WHS*.
    - Jeśli używasz własnych danych, wybierz arkusz musi mieć ustawienie **Sprawdź lokalizację pobrania** na *Nie* i opcję **Zarządzanie kwarantanną** na wartość *Nie*.
1. Ustaw **Referencje** na *Zamowienie zakupu*.
1. Ustaw **Numer konta** na *1001*.
1. Ustaw wartość **Numer** zamówienia zakupu wskazanego dla tego wykonania.

    ![Arkusz przyjęcia pozycji.](../media/item-arrival-journal-header.png "Arkusz przyjęcia pozycji")

1. Wybierz przycisk **OK**, aby utworzyć nagłówek arkusza.
1. W sekcji **Wiersze arkusza** wybierz opcję **Dodaj wiersz** i wprowadź następujące dane:
    - **Numer towaru** – Ustaw na *M9200*. Ustawienia **lokalizacji,** **magazynu** i **ilości** zostaną ustawione na podstawie danych transakcji magazynowej dla 10 palet (1000 szt.).
    - **Lokalizacja** — ustawiono na *001*. Ta lokalizacja nie śledzi numerów identyfikacyjnego.

    ![Wiersz arkusza przyjęcia towaru.](../media/item-arrival-journal-line.png "Wiersz arkusza rpzyjęcia towaru")

    > [!NOTE]
    > Pole **Data** określa dzień, kiedy dostępna ilość tego towaru zostanie zarejestrowana w magazynie.  
    >
    > Pole **Identyfikator partii** zostanie wypełnione przez system, jeśli można je unikatowo zidentyfikować na podstawie dostarczonych informacji. W przeciwnym razie należy go dodać ręcznie. To pole jest wymagane i łączy tę rejestrację z określonym wierszem dokumentu źródłowego.  

1. W okienku akcji wybierz pozycję **Weryfikacja**. Spowoduje to sprawdzenie, czy arkusz jest gotowy do zaksięgowania. Jeżeli weryfikacja przyniesie wynik negatywny, trzeba naprawić błędy, zanim będzie można zaksięgować arkusz.  
1. Zostanie otwarte okno dialogowe **Sprawdzanie arkusza**. Kliknij przycisk **OK**.
1. Sprawdzanie Paska wiadomości. Powinien tam być komunikat z informacją, że operacja została wykonana.  
1. W okienku akcji wybierz pozycję **Księguj**.
1. Zostanie otwarte okno dialogowe **Księgowanie arkusza**. Kliknij przycisk **OK**.
1. Sprawdzanie Paska wiadomości. Powinien tam być komunikat z informacją, że operacja została wykonana.
1. Wybierz opcje **Funkcje > Przyjęcie produktu** w okienku akcji, aby zaktualizować wiersz zamówienia zakupu i zakwitować przyjęcie produktów.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
