---
title: Przetwarzanie ponagleń
description: W tej procedurze pokazano sposób tworzenia, drukowania i księgowania ponagleń.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 12/04/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 8a3f74d2891c050294e089eae14ba2386449d7c9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "358860"
---
# <a name="process-collection-letters"></a>Przetwarzanie ponagleń

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób tworzenia, drukowania i księgowania ponagleń. W zadaniu wykorzystano firmę demonstracyjną USMF.

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Konfigurowanie kolejności ponagleń w profilu księgowania
1. Wybierz kolejno opcje **Kredyty i windykacja > Ustawienia > Profile księgowania odbiorców**.
2. Kliknij przycisk **Edytuj**.
3. Z listy rozwijanej wybierz numer kolejny ponaglenia. Jeśli nie chcesz generować ponagleń dla transakcji przy użyciu tego profilu księgowania, pozostaw to pole puste.  
4. Rozwiń kartę Restrykcje tabeli pozwala na zmianę sposobu przetwarzania ponagleń. Jeśli to pole ma ustawioną wartość **Tak**, ponaglenia będą tworzone dla tego profilu księgowania.  

## <a name="create-collection-letters"></a>Tworzenie ponagleń
1. Wybierz kolejno opcje **Kredyty i windykacja > Ponaglenie > Utwórz ponaglenia**.
2. Wybierz typy transakcji, dla których będą generowane ponaglenia. Wszystkie otwarte transakcje dla tych typów zostaną uwzględnione w obliczeniach.  
2. W polu **Ponaglenie** wybierz opcję.
3. Wprowadź datę ponaglenia.
4. Jeśli w polu **Użyj profilu księgowania z** zmieniono wartość na **Wybierz**, wybierz profil księgowania. Dostępne są dwa profile księgowania:   
   - **Konto** — Dla każdej noty odsetkowej używanie profilu księgowania, który został przypisany do konta odbiorcy.   
   - **Wybierz** — Zostanie użyty profil księgowania wybrany w polu **Profil księgowania**.  
5. Rozwiń sekcję **Rekordy do uwzględnienia**.
6. Kliknij przycisk **Filtr**.
7. W polu **Kryteria** wpisz identyfikator odbiorcy. Na przykład wpisz „US-001”.
8. Kliknij przycisk **OK**.
9. Kliknij przycisk **OK**.

## <a name="print-collection-letters"></a>Drukowanie ponagleń
1. Wybierz kolejno opcje **Kredyty i windykacja > Ponaglenie > Przejrzyj i przetwórz ponaglenia**.
2. W polu **Stan** wybierz opcję **Utworzono**.
3. W polu **Wydrukowane** wybierz opcję **Nie wydrukowano**.
4. Kliknij przycisk **Drukuj**.
5. Kliknij opcję **Tekst ponaglenia**.
6. Rozwiń sekcję **Rekordy do uwzględnienia**.
7. Wprowadź graniczną datę księgowania.
8. Kliknij przycisk **OK**, aby wydrukować ponaglenie.
9. Księgowanie ponaglenia.
   1. Kliknij przycisk **Księguj**.
   2. Wprowadź datę księgowania ponaglenia.
   3. Rozwiń sekcję **Rekordy do uwzględnienia**.
   4. Kliknij przycisk **OK**.
   5. W polu **Stan** wybierz opcję **Zaksięgowano**.
   6. W polu **Wydrukowane** wybierz opcję.

## <a name="control-collection-letters-at-the-customer-level"></a>Kontrolowanie arkuszy ponagleń na poziomie odbiorcy
Można też skonfigurować ponaglenia na poziomie odbiorcy, aby kod ponaglenia dla każdej transakcji był śledzony, ale przetwarzanie ponaglenia opierało się na jednym poziomie ponaglenia zapisanego dla danego odbiorcy. Pojedyncze ponaglenie będzie zawierało wszystkie transakcje, które są zaległe dla odbiorcy. Ponieważ liczba dni prolongaty jest teraz śledzona na poziomie odbiorcy, następne ponaglenie nie zostanie wysłane aż do upłynięcia dni prolongaty dla następnego ponaglenia w sekwencji, nawet jeśli transakcje staną się zaległe od momentu wysłania ostatniego ponaglenia. Ta opcja zmniejsza liczbę ponagleń wysyłanych do odbiorcy. 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a>Konfigurowanie odbiorcy do kontrolowania arkuszy ponagleń na poziomie odbiorcy
1.  Przejdź do **Kredyty i windykacja > Ustawienia > Parametry modułu rozrachunków z odbiorcami** i kliknij kartę **Windykacje**. 
2.  Zmień wartość **Utwórz ponaglenie dla** na **Obiorcy**. 
3.  Wybierz kolejno opcje **Kredyty i windykacja > Ponaglenie > Przejrzyj i przetwórz ponaglenia**. Tylko jedno ponaglenie zostanie wygenerowane dla odbiorcy ze wszystkimi zaległymi transakcjami.

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a>Ignorowanie płatności i not kredytowych przy obliczaniu kodu ponaglenia
Jeśli uwzględnisz płatności i noty kredytowe w transakcjach umieszczanych w ponagleniach, możesz mieć płatności lub noty kredytowe, które będą wywoływały ponaglenie. Możesz kontrolować sposób kontrolowania kodu ponaglenia przez płatności i noty kredytowe, zmieniając wartość parametru **Ignoruj płatności i noty kredytowe przy obliczaniu kodu ponaglenia**. 

Aby zignorować płatności i noty kredytowe przy obliczaniu kodu ponaglenia, wykonaj następujące czynności.
1. Przejdź do **Kredyty i windykacja > Ustawienia > Parametry modułu rozrachunków z odbiorcami** i kliknij kartę **Windykacje**. 
2. Zmień wartość opcji **Ignoruj płatności i noty kredytowe przy obliczaniu kodu ponaglenia** na **Tak**.
