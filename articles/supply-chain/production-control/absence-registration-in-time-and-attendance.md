---
title: "Rejestracja nieobecności w module Czas i frekwencja"
description: "W tym temacie opisano sposób obsługi nieobecności w module Czas i frekwencja."
author: johanhoffmann
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 477724e6211a084638e8a0b7133f60edef07b3ad
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="absence-registration-in-time-and-attendance"></a>Rejestracja nieobecności w module Czas i frekwencja

[!include[banner](../includes/banner.md)]

W tym temacie opisano koncepcję nieobecności i wyjaśniono sposób obsługi nieobecności w module Czas i frekwencja.

## <a name="absence-that-is-based-on-regular-work-hours"></a>Nieobecność w normalnych godzinach pracy

Pracownicy są uznawani za nieobecnych, jeżeli nie pracują w normalnych godzinach pracy. Normalne godziny pracy są zdefiniowane w standardowym profilu czasu pracownika.

Przykład: pracownik pracuje w profilu dziennym, w którym wejście ustawiono na godzinę 7:00, a wyjście na godzinę 15:00. Jeżeli pracownik zarejestruje wejście o 9:00, jest uznawany za nieobecnego od 7:00 to 9:00 tego dnia.

W takim przypadku pracownikowi zostaje wyświetlony monit o wprowadzenie powodu nieobecności. Mogą określić powód, wybierając kod nieobecności.

## <a name="absence-codes"></a>Kody nieobecności

Kody nieobecności określają różne typy nieobecności. Kody nieobecności są definiowane przez firmę.

Do kodów nieobecności można zastosować różne zasady. Kod nieobecności można na przykład skonfigurować w celu odjęcia lub dodania płacy.

Przykładowo firma definiuje kod nieobecności **Spóźnienie** używany przez pracowników w przypadku spóźnienia bez określonego powodu. Firma określa także kod nieobecności **Kurs wewnętrzny** używany przez pracowników w odniesieniu do czasu poświęconego na udział w kursie wewnętrznym. Te kody nieobecności można skonfigurować tak, aby kod **Spóźnienie** zmniejszał płacę pracownika, ale kod **Kurs wewnętrzny** nie zmniejszał płacy pracownika.

Można skonfigurować automatyczne kody nieobecności. Tych kodów nieobecności można użyć do obliczenia czasu pracy pracownika, jeżeli nie zarejestrowano nieobecności. Profil czasu pracownika określa, czy używany jest kod nieobecności czasu standardowego czy czasu elastycznego.

### <a name="set-up-standard-time-and-flex-time"></a>Konfigurowanie czasu standardowego i czasu elastycznego

- Parametry czas standardowego i czasu elastycznego można skonfigurować, używając opcji **Automatyczne wstawianie nieobecności** i **Automatyczne wstawianie elastycznego czasu pracy-** na stronie **Parametry modułu Czas i frekwencja**.

## <a name="absence-groups"></a>Grupy nieobecności

Kody nieobecności są zgrupowane w grupach nieobecności. Grupy nieobecności służą do grupowania kodów nieobecności o wspólnych cechach. Przykłady obejmują kody nieobecności dotyczące nieobecności usprawiedliwionej lub nieobecności z powodu wizyty lekarskiej, obowiązków sędziego przysięgłego lub choroby dziecka.

## <a name="planned-absence"></a>Planowana nieobecność

Jeżeli wiadomo, że pracownik będzie nieobecny przez pewien okres, taki jak zbliżające się wakacje, można użyć zaplanowanej nieobecności. Planowaną nieobecność można ustawić, konfigurując kod nieobecności tak, aby uwzględniał planowaną nieobecność. Podczas konfigurowania planowanej nie obecności nie jest wyświetlany monit o podanie kodu nieobecności podczas okresu nieobecności, gdy obliczane są rejestracje czasu użytkownika. Planowaną obecność można zdefiniować dla jednego pracownika lub można zdefiniować zadanie wsadowe w celu zbiorczej aktualizacji planowanej nieobecności pracowników.

### <a name="set-up-planned-absence"></a>Ustawianie planowanej nieobecności

1. Wybierz opcję **Zasoby ludzkie** &gt; **Pracownicy** &gt; **Pracownicy etatowi** i wybierz pracownika.
2. Wybierz opcję **Czas** &gt; **Przypisania czasu** &gt; **Rejestracja czasu nieobecności** i ustaw planowaną nieobecność.

## <a name="interrupted-planned-absence"></a>Przerwana planowana nieobecność

Po zastosowaniu opcji **Przerwij** przy ustawianiu planowanej nieobecności zostanie ona przerwana, jeżeli pracownik zaloguje się w okresie planowanej nieobecności. Planowana obecność zostanie oznaczona jako **Przerwana** i nie będzie miała wpływu na przyszłe obliczenia.

### <a name="set-up-a-planned-absence-for-interruption"></a>Ustawianie planowanej nieobecności dla przerwania

1. Otwórz stronę **Rejestracja czasu nieobecności** zgodnie z opisem w procedurze ustawiania planowanej nieobecności.
2. Wybierz opcję **Przerwij**.

Opcja **Przerwij** ma zastosowanie, gdy czas jest rejestrowany za pomocą terminala produkcji lub urządzenia produkcji. Ta opcja nie ma zastosowania, jeżeli rejestracje są wprowadzane na stronach obliczania i zatwierdzania lub na stronie **Elektroniczna karta czasowa**.

## <a name="examples-of-the-use-of-absence-in-a-flex-profile"></a>Przykłady użycia nieobecności w profilu elastycznym

Poniższe trzy przykłady przedstawiają sposób obliczania nieobecności w profilu zawierającym okresy elastyczne.

W przykładach używany jest poniższy profil.

| Wejście | Czas standardowy    | Przerwa             | Czas standardowy | Elastyczny czas pracy -        | Wyjście | Elastyczny czas pracy (+)        |
|----------|------------------|-------------------|---------------|--------------|-----------|--------------|
| 8:00     | 9:00 do 11:30 | 11:30 do 12:00 | 12:00 do 15:00 | 15:00 do 16:00 | 16:00      | 16:00 do 18:00 |

### <a name="example-1-signing-out-during-a-flex--period"></a>Przykład 1: Wylogowanie podczas okresu elastycznego-

Pracownik rejestruje się przy wejściu o 8:00, a przy wyjściu o 15:30. W tym przypadku, ponieważ pracownik rejestruje się przy wyjściu podczas okresu elastycznego-, nieobecność nie jest obliczana, a od salda elastycznego pracownika odliczane jest pół godziny.

### <a name="example-2-signing-out-in-during-standard-time-period"></a>Przykład 2: Wylogowanie w okresie czasu standardowego

Pracownik rejestruje się przy wejściu o 8:00, a przy wyjściu o 14:30. W tym przypadku, ponieważ pracownik rejestruje się przy wyjściu podczas okresu standardowego, nieobecność jest obliczana od 14:30 do 16:00 i rejestrowany jest okres nieobecności wynoszący 1,5 godziny. Dla tego okresu wymagany jest kod nieobecności.

### <a name="example-3-signing-out-during-a-flex-period"></a>Przykład 3: Wylogowanie podczas okresu elastycznego+

Pracownik rejestruje się przy wejściu o 8:00, a przy wyjściu o 16:30. W tym przypadku, ponieważ pracownik rejestruje się przy wyjściu podczas okresu elastycznego+, nieobecność nie jest obliczana, a do salda elastycznego pracownika dodawane jest pół godziny.

## <a name="absence-in-the-calculation-and-approval-process"></a>Nieobecność w obliczeniu i proces zatwierdzania

Rejestracje czasu pracownika muszą zostać obliczone i zatwierdzone przed przeniesieniem do systemu listy płac jako elementy płac.

Osoba zatwierdzająca może zmienić rejestracje czasu pracownika. Osoba zatwierdzająca także zmienić wszystkie nieobecności, które zarejestrował pracownik. Jeżeli osoba zatwierdzająca ręcznie wprowadzi okres, który zawiera kod nieobecności, kod nieobecności dla tego okresu nie zostanie zastąpiony przez domyślny kod nieobecności z parametrów modułu Czas i frekwencja.

Przykładowo pracownica rejestruje się przy wyjściu o 10:00 i wybiera kod nieobecności oznaczający, że się spóźniła. Następnie informuje przełożonego, ze ma wizytę u lekarza od 8:00 do 10:00. Wizyta u lekarza nie powinna spowodować zmniejszenia płacy pracownika. Dlatego w tym przypadku przełożony może dostosować dwugodzinną nieobecność od 8:00 do 10:00, ręcznie wprowadzając kod nieobecności, który oznacza chorobę przez te dwie godziny.

### <a name="calculate-and-approve-absence"></a>Obliczanie i zatwierdzanie nieobecności

- Wybierz opcję **Czas i frekwencja** &gt; **Przejrzyj i zatwierdź** &gt; **Zatwierdź lub oblicz**.

