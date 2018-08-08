--- 
title: "Przetwarzanie ponagleń"
description: "W tej procedurze pokazano sposób tworzenia, drukowania i księgowania ponagleń."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dc837ea6513992a5f94e48baa366e279df297866
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="process-collection-letters"></a>Przetwarzanie ponagleń

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia, drukowania i księgowania ponagleń. W zadaniu wykorzystano firmę demonstracyjną USMF.


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Konfigurowanie kolejności ponagleń w profilu księgowania
1. Wybierz kolejno opcje Kredyty i windykacja > Ustawienia > Profile księgowania odbiorców.
2. Kliknij przycisk Edytuj.
    * Z listy rozwijanej wybierz numer kolejny ponaglenia. Jeśli nie chcesz generować ponagleń dla transakcji przy użyciu tego profilu księgowania, pozostaw to pole puste.  
    * Karta Restrykcje tabeli pozwala na zmianę sposobu przetwarzania ponagleń. Jeśli to pole ma ustawioną wartość Tak, ponaglenia będą tworzone dla tego profilu księgowania.  
3. Zamknij stronę.

## <a name="create-collection-letters"></a>Tworzenie ponagleń
1. Wybierz kolejno opcje Kredyty i windykacja > Ponaglenie > Utwórz ponaglenia.
    * Należy wybrać typy transakcji, dla których będą generowane ponaglenia. Wszystkie otwarte transakcje dla tych typów zostaną uwzględnione w obliczeniach.  
2. W polu Ponaglenie wybierz opcję.
3. Wprowadź datę ponaglenia.
    * Istnieją dwie opcje profili księgowania:   Konto — Dla każdej noty odsetkowej używanie profilu księgowania, który został przypisany do konta odbiorcy.   Wybierz — Zostanie użyty profil księgowania wybrany w polu Profil księgowania.  
    * Jeśli w polu „Użyj profilu księgowania z” zmieniono wartość na „Wybierz”, wybierz profil księgowania.  
4. Rozwiń sekcję Rekordy do uwzględnienia.
5. Kliknij przycisk Filtr.
6. W polu Kryteria wprowadź identyfikator odbiorcy. Na przykład wpisz „US-001”.
7. Kliknij przycisk OK.
8. Kliknij przycisk OK.

## <a name="print-collection-letters"></a>Drukowanie ponagleń
1. Wybierz kolejno opcje Kredyty i windykacja > Ponaglenie > Przejrzyj i przetwórz ponaglenia.
2. W polu Stan wybierz opcję „Utworzono”.
3. W polu Wydrukowane wybierz opcję „Nie wydrukowano”.
4. Kliknij przycisk Drukuj.
5. Kliknij opcję Tekst ponaglenia.
6. Rozwiń sekcję Rekordy do uwzględnienia.
7. Wprowadź graniczną datę księgowania.
8. Kliknij przycisk OK, aby wydrukować ponaglenie.

## <a name="post-the-collection-letter"></a>Księgowanie ponaglenia
1. Kliknij przycisk Księguj.
2. Wprowadź datę księgowania ponaglenia.
3. Rozwiń sekcję Rekordy do uwzględnienia.
4. Kliknij przycisk OK.
5. W polu Stan wybierz opcję „Zaksięgowano”.
6. W polu Wydrukowane wybierz opcję.


