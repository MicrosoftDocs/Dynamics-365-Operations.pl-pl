--- 
title: Konfigurowanie automatycznego uzgadniania frachtu
description: "Ta procedura pokazuje, jak skonfigurować dane dla automatycznego uzgadniania frachtu."
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 61b795d52d4d2586db7f42a976790ee8608e179b
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-automatic-freight-reconciliation"></a>Konfigurowanie automatycznego uzgadniania frachtu

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje, jak skonfigurować dane dla automatycznego uzgadniania frachtu. Zwykle wykonuje to kierownik magazynu. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.


## <a name="set-up-the-freight-bill-type"></a>Konfigurowanie typu opłaty frachtowej
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Uzgodnienie frachtu > Typ opłaty frachtowej.
    * Typ dokumentu opłaty frachtowej określa, jak powinny być uzgadniane dokumenty opłat frachtowych i faktury przewoźników.  
2. Kliknij przycisk Nowy.
3. W polu Typ opłaty frachtowej wpisz wartość.
4. W polu Montaż aparatu wpisz „Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer”.
    * Jest to biblioteka standardowych kodów aparatu uzgadniania w zarządzaniu transportem.  
5. W polu Klasa aparatu wpisz „Microsoft.Dynamics.Ax.Tms.dll”.
    * Jest to standardowa klasa aparatu uzgadniania w zarządzaniu transportem.  
6. Kliknij przycisk Nowy.
7. W polu Opis wybierz wartość, która powinna być zgodna na dokumencie opłaty frachtowej i fakturze przewoźnika.  
8. W polu Wymagane dopasowanie wybierz opcję „Tak”.
    * Jeśli w tym polu ustawisz wartość Tak, oznacza to, że wartość wybrana w polu Opis musi być zgodna z wartościami na dokumencie opłaty frachtowej i na fakturze przewoźnika. Jeśli zostanie ustawiona wartość Nie, pole może być puste w jednym z tych dokumentów.  
9. Kliknij przycisk Zapisz.

## <a name="set-up-the-freight-bill-type-assignment"></a>Konfigurowanie przypisania typu opłaty frachtowej
1. Zamknij stronę.
2. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Uzgodnienie frachtu > Przypisania typu opłaty frachtowej.
    * Przypisanie typu dokumentu opłaty frachtowej służy do określania, który typ dokumentu opłaty frachtowej jest używany dla określonego przewoźnika.   
3. Kliknij przycisk Nowy.
4. Wprowadź lub wybierz wartość w polu Tryb.
5. Wprowadź lub wybierz wartość w polu Firma przewozowa.
6. W polu Typ opłaty frachtowej wybierz typ dokumentu opłaty frachtowej, który został wcześniej utworzony.
7. Zamknij stronę.

## <a name="set-up-the-audit-master"></a>Konfigurowanie głównej inspekcji
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Uzgodnienie frachtu > Główna inspekcja.
    * Główna inspekcja definiuje granice tolerancji dla automatycznego uzgadniania frachtu. Określa, o ile kwoty pieniężne na dokumencie opłaty frachtowej i fakturze przewoźnika mogą się różnić, aby jeszcze następowało uzgodnienie. Definiuje również sposób obsługi niezgodności.  
2. Kliknij przycisk Nowy.
3. W polu Identyfikator głównej inspekcji wpisz wartość.
4. W polu Firma przewozowa zaznacz tę samą firmę przewozową, jak poprzednio.
5. W polu Typ opłaty frachtowej wybierz typ dokumentu opłaty frachtowej, który został wcześniej utworzony.
6. Rozwiń sekcję Tolerancja.
7. W polu Minimalny poziom tolerancji wpisz liczbę.
8. W polu Maksymalny poziom tolerancji wpisz liczbę.
9. Rozwiń sekcję Wynik.
10. W polu Kod przyczyny nadpłaty wprowadź lub wybierz wartość.
    * Jeśli kwoty pieniężne różnią się na dokumencie opłaty frachtowej i fakturze przewoźnika, kody przyczyn nadpłaty i niedopłaty określają konta, na których należy zarejestrować różnicę, o ile tylko różnica mieści się w granicach tolerancji.  
11. W polu Kod przyczyny niedopłaty wprowadź lub wybierz wartość.
12. Zamknij stronę.


