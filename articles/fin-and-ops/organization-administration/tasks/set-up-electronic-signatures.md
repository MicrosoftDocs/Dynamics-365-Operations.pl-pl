--- 
title: "Konfigurowanie podpisów elektronicznych"
description: "Użyj tej procedury do skonfigurowania podpisów elektronicznych."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 43ac3aecd9290e496fc8dd237c0d09b60638f442
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-electronic-signatures"></a>Konfigurowanie podpisów elektronicznych

[!include[task guide banner](../../includes/task-guide-banner.md)]

Użyj tej procedury do skonfigurowania podpisów elektronicznych. Podpis elektroniczny potwierdza tożsamość osoby, która ma rozpocząć lub zatwierdzić jakiś proces obliczeniowy. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DAT.


## <a name="enable-the-electronic-signature-configuration-key"></a>Włączanie funkcji Klucz konfiguracji Podpis elektroniczny
1. Wybierz kolejno opcje Administrowanie systemem > Ustawienia > Konfiguracja licencji.
2. W drzewie rozwiń węzeł „Administracja”.
    * Upewnij się, że jest zaznaczone pole wyboru Podpis elektroniczny.  
    * Jeśli nie jest zaznaczone pole wyboru Podpis elektroniczny, należy włączyć tryb konserwacji. Tryb konserwacji można włączyć w tym środowisku, uruchamiając zadanie konserwacji z poziomu usługi Lifecycle Services albo używając lokalnie narzędzia Deployment.Setup.  
3. Zamknij stronę.

## <a name="set-up-electronic-signature-parameters"></a>Konfigurowanie parametrów podpisu elektronicznego
1. Wybierz kolejno opcje Administrowanie organizacją > Ustawienia > Podpis elektroniczny > Parametry podpisu elektronicznego.
2. Kliknij przycisk Edytuj.
3. W polu Powiadomienie wpisz wartość.
    * Wprowadź powiadomienie, które osoby podpisujące będą otrzymywać w przypadku żądania podpisu. Możesz wprowadzić dowolny tekst. Zazwyczaj taki tekst wyjaśnia użytkownikowi, co to znaczy podpisać dokument elektronicznie.  
    * Jeśli chcesz wprowadzić tekst powiadomienia w dodatkowych językach, kliknij przycisk Tłumaczenia.  
4. Kliknij przycisk Zapisz.
5. Zamknij stronę.

## <a name="set-up-reason-codes-for-electronic-signatures"></a>Konfigurowanie kodów przyczyn dla podpisów elektronicznych
1. Wybierz kolejno opcje Administrowanie organizacją > Ustawienia > Podpis elektroniczny > Kody przyczyn podpisu elektronicznego.
2. Kliknij przycisk Nowy.
    * Kody przyczyn trzeba skonfigurować przez rozpoczęciem korzystania z podpisów elektronicznych. Prawidłowy kod przyczyny jest wymagany podczas podpisywania dokumentu.     Osoba podpisująca wybiera kod przyczyny, aby wskazać cel podpisu elektronicznego. Kodu przyczyny można na przykład użyć w celu wskazania zgody prawnej.  
3. W polu Kod przyczyny wpisz wartość.
4. Wypełnij pole Opis.
    * W razie potrzeby wprowadź dodatkowe kody przyczyn.  
5. Kliknij przycisk Zapisz.
6. Zamknij stronę.

## <a name="require-electronic-signatures-for-existing-processes"></a>Wymaganie używania podpisów elektronicznych do istniejących procesów
1. Wybierz kolejno opcje Administrowanie organizacją > Ustawienia > Podpis elektroniczny > Wymagania dotyczące podpisu elektronicznego.
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz proces wymagający podpisów elektronicznych.  
3. Zaznacz lub wyczyść pole wyboru Wymagany jest podpis.
    * Powtórz te kroki dla każdego procesu, który wymaga podpisów elektronicznych.  
4. Kliknij przycisk Zapisz.

## <a name="create-a-custom-requirement-for-electronic-signatures"></a>Tworzenie niestandardowego wymagania dotyczącego podpisów elektronicznych
1. Kliknij przycisk Nowy.
2. Zaznacz lub wyczyść pole wyboru Wymagany jest podpis.
3. W polu Nazwa wpisz nazwę procesu wymagającego podpisów elektronicznych.
4. W polu Nazwa tabeli kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście znajdź i zaznacz tabelę, w której są przechowywane dane wymagające podpisu.
6. Na liście kliknij łącze w wybranym wierszu.
7. W polu Nazwa pola kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście znajdź i zaznacz pole w tabeli, które ma być monitorowane.
9. Na liście kliknij łącze w wybranym wierszu.
    * Określ, kiedy ma być wymagany podpis.     Wybierz opcję Zawsze, jeśli podpis ma być wymagany przy każdej zmianie danych pola.     Wybierz opcję Tylko, aby określić, że podpis ma być wymagany tylko pod pewnymi warunkami. Jeśli wybierzesz opcję Tylko, należy również wybrać jedną z następujących opcji: Przy wstawianiu rekordu, Przy aktualizacji rekordu lub Przy usuwaniu rekordu.  
10. Kliknij przycisk Zapisz.
11. Zamknij stronę.

