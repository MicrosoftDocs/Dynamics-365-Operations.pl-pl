---
title: Przetwarzanie ponagleń
description: W tym temacie pokazano sposób tworzenia, drukowania i księgowania ponagleń.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 2b8ce102086535a5462d3fa0e8ac76e9ec3dd15c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446734"
---
# <a name="process-collection-letters"></a>Przetwarzanie ponagleń

[!include [banner](../../includes/banner.md)]

W tym temacie pokazano sposób tworzenia, drukowania i księgowania ponagleń. W zadaniu wykorzystano firmę demonstracyjną USMF.

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Konfigurowanie kolejności ponagleń w profilu księgowania
1. Otwórz **Okienko nawigacji > Moduły > Kredyty i windykacja > Ustawienia > Profile księgowania odbiorców**.
2. Kliknij przycisk **Edytuj**.
3. Z listy rozwijanej wybierz numer kolejny ponaglenia. Jeśli nie chcesz generować ponagleń dla transakcji przy użyciu tego profilu księgowania, pozostaw to pole puste.  
4. Rozwiń kartę **Restrykcje tabeli** pozwala na zmianę sposobu przetwarzania ponagleń. Jeśli to pole ma ustawioną wartość **Tak**, ponaglenia będą tworzone dla tego profilu księgowania.  

## <a name="create-collection-letters"></a>Tworzenie ponagleń
1. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Kredyty i windykacja > Ponaglenie > Utwórz ponaglenia**.
2. Wybierz typy transakcji, dla których będą generowane ponaglenia. Wszystkie otwarte transakcje dla tych typów zostaną uwzględnione w obliczeniach.  
3. W polu **Ponaglenie** wybierz opcję.
4. W polu **Data ponaglenia** wprowadź datę ponaglenia.
5. Jeśli w polu **Użyj profilu księgowania z** zmieniono wartość na **Wybierz**, wybierz profil księgowania. Dostępne są dwa profile księgowania:   

   - **Konto** — Dla każdej noty odsetkowej używanie profilu księgowania, który został przypisany do konta odbiorcy.   
   - **Wybierz** — Zostanie użyty profil księgowania wybrany w polu **Profil księgowania**.  

6. Rozwiń sekcję **Rekordy do uwzględnienia**.
7. Wybierz **Filtry**.
8. W polu **Kryteria** wpisz identyfikator odbiorcy. Na przykład wpisz „US-001”.
9. Kliknij przycisk **OK**.
10. Kliknij przycisk **OK**.

## <a name="print-collection-letters"></a>Drukowanie ponagleń
1. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Kredyty i windykacja > Ponaglenie > Przejrzyj i przetwórz ponaglenia**.
2. W polu **Stan** wybierz opcję **Utworzono**.
3. W polu **Wydrukowane** wybierz opcję **Nie wydrukowano**.
4. Wybierz **Drukuj**.
5. Wybierz **Tekst ponaglenia**.
6. W sekcji **Parametry** wprowadź datę graniczną księgowania.
7. Rozwiń sekcję **Rekordy do uwzględnienia** uwzględnić, a następnie wprowadź szczegóły noty ponaglenia.
8. Wybier **OK**, aby wydrukować ponaglenie.
9. Księgowanie ponaglenia.

    1. Wybierz opcję **Zaksięguj**.
    1. Wprowadź datę księgowania ponaglenia.
    1. Rozwiń sekcję **Rekordy do uwzględnienia**.
    1. Kliknij przycisk **OK**.
    1. W polu **Stan** wybierz opcję **Zaksięgowano**.
    1. W polu **Wydrukowane** wybierz opcję.

## <a name="control-collection-letters-at-the-customer-level"></a>Kontrolowanie arkuszy ponagleń na poziomie odbiorcy
Jeśli ponaglenia są skonfigurowane na poziomie transakcji, dla odbiorcy może być generowanych wiele listów na podstawie przedawnienia transakcji. Jeśli transakcje są wyświetlane w różnych sekwencjach listów, dla każdej grupy transakcji zaległych dla odbiorcy zostaną wygenerowane oddzielne ponaglenia. W związku z tym pojedynczy odbiorca może na przykład uzyskać jedno ponaglenie dla transakcji, które są zaległe 60 dni i inne ponaglenie dla transakcji, które są zaległe 90 dni. 

Każde ponaglenie jest również skojarzone z kodem ponaglenia. Kod ponaglenia jest skojarzony z poszczególnymi transakcjami i jest używany do ustalania, kiedy dla każdej transakcji ma być generowane następne ponaglenie. Jeśli na przykład transakcja jest opóźniona ponad 30 dni, kod ponaglenia określa, że następne ponaglenie zostanie wysłane, gdy transakcja będzie opóźniona przez 60 dni, jeśli nie zostanie do tego czasu zaksięgowana. 

Ponaglenia można również skonfigurować na poziomie odbiorcy. W takim przypadku kod ponaglenia dla każdej transakcji jest śledzony, ale przetwarzanie ponaglenia będzie opierało się na jednym poziomie ponaglenia zapisanego dla danego odbiorcy. Pojedyncze ponaglenie będzie zawierało wszystkie transakcje, które są zaległe dla odbiorcy. Ponieważ liczba dni prolongaty jest teraz śledzona na poziomie odbiorcy, następne ponaglenie nie zostanie wysłane aż do upłynięcia dni prolongaty dla następnego ponaglenia w sekwencji, nawet jeśli transakcje staną się zaległe od momentu wysłania ostatniego ponaglenia. Ta opcja pomaga zmniejszać liczbę ponagleń, które muszą być wysłane do każdego odbiorcy.

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a>Konfigurowanie odbiorcy do kontrolowania arkuszy ponagleń na poziomie odbiorcy
1.  Przejdź do **Okienko nawigacji > Moduły > Kredyty i windykacja > Ustawienia > Parametry modułu rozrachunków z odbiorcami** i wybierz kartę **Windykacje**. 
2.  Zmień wartość **Utwórz ponaglenie dla** na **Obiorcy**. 
3.  Wybierz kolejno opcje **Okienko nawigacji > Moduły > Kredyty i windykacja > Ponaglenie > Przejrzyj i przetwórz ponaglenia**. Tylko jedno ponaglenie zostanie wygenerowane dla odbiorcy ze wszystkimi zaległymi transakcjami.

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a>Ignorowanie płatności i not kredytowych przy obliczaniu kodu ponaglenia
Jeśli uwzględnisz płatności i noty kredytowe w transakcjach umieszczanych w ponagleniach, możesz mieć płatności lub noty kredytowe, które będą wywoływały ponaglenie. Możesz kontrolować sposób kontrolowania kodu ponaglenia przez płatności i noty kredytowe, zmieniając wartość parametru **Ignoruj płatności i noty kredytowe przy obliczaniu kodu ponaglenia**. 

Aby zignorować płatności i noty kredytowe przy obliczaniu kodu ponaglenia, wykonaj następujące czynności.

1. Przejdź do **Okienko nawigacji > Moduły > Kredyty i windykacja > Ustawienia > Parametry modułu rozrachunków z odbiorcami** i kliknij kartę **Windykacje**. 
2. Zmień wartość opcji **Ignoruj płatności i noty kredytowe przy obliczaniu kodu ponaglenia** na **Tak**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]