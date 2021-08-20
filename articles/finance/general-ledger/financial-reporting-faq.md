---
title: Raportowanie finansowe — często zadawane pytania
description: Ten temat zawiera odpowiedzi na niektóre często zadawane pytania dotyczące raportowania finansowego.
author: jiwo
ms.date: 07/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: dd493e855e45362c1681dc9cdfbbcb71f7627d64624cd093eadab32fd966c174
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733618"
---
# <a name="financial-reporting-faq"></a>Raportowanie finansowe — często zadawane pytania

Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące raportowania finansowego.

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a>Jak ograniczyć dostęp do raportu przy użyciu zabezpieczeń drzewa?

Na poniższym przykładzie pokazano, jak ograniczyć dostęp do raportu przy użyciu zabezpieczeń drzewa.

Firma demonstracyjna USMF ma raport **bilansowy**, do którego nie wszyscy użytkownicy raportowania finansowego powinni mieć dostęp. W celu ograniczenia dostępu do jednego raportu można użyć drzewa zabezpieczeń — dzięki temu dostęp do niego będą mieć tylko wybrani użytkownicy.

1. Zaloguj się w rozwiązaniu Financial Reporter Report Designer.
2. W celu utworzenia nowej definicji drzewa wybierz **Plik \> Nowy \> Definicja drzewa**.
3. Naciśnij (lub kliknij) dwukrotnie wiersz **Podsumowanie** w kolumnie **Zabezpieczenia jednostki**.
4. Wybierz opcję **Użytkownicy i grupy**.
5. Wybierz użytkowników lub grupy, które wymagają dostępu do raportu.
6. Wybierz opcję **Zapisz**.
7. W definicji raportu dodaj nową definicję drzewa.
8. W definicji drzewa wybierz opcję **Ustawienie**. Następnie w obszarze **Wybór jednostki raportowania** wybierz opcję **Uwzględnij wszystkie jednostki**.

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a>Jak określić, które konta nie pasują do moich sald?

Jeśli masz raport, który nie zawiera pasujących sald, zastosuj następujące procedury w celu zidentyfikowania każdego konta i odchylenia.

### <a name="in-financial-reporter-report-designer"></a>W Financial Reporter Report Designer

1. Utwórz nową definicję wiersza.
2. Kliknij opcję **Edycja \> Wstaw wiersze z wymiarów**.
3. Wybierz opcję **MainAccount**.
4. Kliknij przycisk **OK**.
5. Zapisz definicję wiersza.
6. Utwórz nową definicję kolumny.
7. Utwórz nową definicję raportu.
8. Wybierz opcję **Ustawienia** i usuń jej zaznaczenie.
9. Wygeneruj raport. 
10. Wyeksportuj raport do programu Microsoft Excel.

### <a name="in-dynamics-365-finance"></a>W Dynamics 365 Finance

1. Przejdź do opcji **Księga główna \> Zapytania i raporty \> Bilans próbny**.
2. Ustaw wartości w następujących polach:

    - **Data początkowa** — wprowadź datę rozpoczęcia roku obrachunkowego.
    - **Data końcowa** — wprowadź datę, dla której generowany jest raport.
    - **Wymiar finansowy** — ustaw wartość tego pola na **Ustawione konto główne**.

3. Wybierz pozycję **Oblicz**.
4. Wyeksportuj raport do programu Excel.

Teraz powinno być możliwe skopiowanie danych z raportu programu Financial Reporter w programie Excel do raportu **Bilans próbny**, by można było porównać kolumny **Saldo zamknięcia**.

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a>Podczas projektowania raportu w programie Report Designer lub podczas generowania raportu finansowego wyświetlany jest następujący komunikat: „Nie można zakończyć operacji z powodu problemu w strukturze dostawcy danych.” W jaki sposób należy zareagować?

Komunikat wskazuje, że wystąpił problem podczas próby pobrania przez system metadanych finansowych ze składnicy danych podczas korzystania z raportowania finansowego. Istnieją dwa sposoby odpowiedzi na ten problem:

- Aby sprawdzić stan integracji danych, należy w programie Report Designer przejść do opcji **Narzędzia \> Stan integracji**. Jeśli integracja jest niekompletna, poczekaj na jej zakończenie. Po otrzymaniu komunikatu ponów próbę wykonania swojej czynności.
- Skontaktuj się z pomocą techniczną, aby zidentyfikować i rozwiązać problem. W systemie mogą być niespójne dane. Inżynierowie pomocy technicznej mogą pomóc w zidentyfikowaniu tego problemu na serwerze i odnalezieniu określonych danych, które mogą wymagać aktualizacji.

## <a name="how-does-the-selection-of-historical-rate-translation-affect-report-performance"></a>Jak wybór historycznego przeliczania stawek wpływa na wydajność raportu?

Historyczna stawka jest zwykle używana ze wstrzymanymi dochodami, własnością, instalacją i wyposażeniem oraz kontami kapitałowymi. Historyczna stawka może być wymagana w oparciu o wytyczne Rady Standardów Rachunkowości Finansowej (FASB) lub Powszechnie Uznawanych Zasadach Rachunkowości (GAAP). Aby uzyskać więcej informacji, zobacz [Możliwości waluty w raportowaniu finansowym](financial-reporting-currency-capability.md).

## <a name="how-many-types-of-currency-rate-are-there"></a>Ile jest rodzajów kursów walutowych?

Dostępne są trzy typy kosztów:

- **Bieżąca stawka** — ten typ jest zwykle używany z kontami bilansowymi. Jest zwykle znany jako *punktowy kurs wymiany* i może być stawką z ostatniego dnia miesiąca lub innej z góry ustalonej daty.
- **Średnia stawka** — ten typ jest zwykle używany z kontami rachunku zysków i strat (zysk/strata). Średnią stawkę można skonfigurować do zwykłej średniej lub średniej ważonej.
- **Historyczna stawka** — ten typ zwykle używany ze wstrzymanymi dochodami, własnością, instalacją i wyposażeniem oraz kontami kapitałowymi. Konta te mogą być wymagane na podstawie wytycznych FASB lub GAAP.

## <a name="how-does-historical-currency-translation-work"></a>Jak działa historyczne przeliczanie walut?

Stawki są specyficzne dla daty transakcji. W związku z tym każda transakcja jest przeliczana indywidualnie na podstawie najbliższego kursu wymiany.

W przypadku historycznego przeliczania walut można użyć wstępnie obliczonych sald okresów zamiast poszczególnych szczegółów transakcji. To zachowanie różni się od zachowania dla bieżącego przeliczania stawki.

## <a name="how-does-historical-currency-translation-affect-performance"></a>Jak historyczne przeliczanie walut wpływa na wydajność?

Gdy dane prezentowane w raportach są aktualizowane, może wystąpić opóźnienie, ponieważ kwoty muszą zostać ponownie obliczone przez sprawdzenie szczegółów transakcji. To opóźnienie jest wyzwalane za każdym razem, gdy stawki są aktualizowane lub księgowanych jest więcej transakcji. Jeśli na przykład tysiące kont są skonfigurowane do historycznego przeliczania kilka razy dziennie, może wystąpić opóźnienie do godziny przed zaktualizowaniem danych w raporcie. Z drugiej strony, jeśli istnieje mniejsza liczba określonych kont, czas przetwarzania aktualizacji danych raportu można skrócić do minut lub mniej.

Podobnie, gdy raporty są generowane przy użyciu przeliczania walut dla kont typu historycznego, wystąpią dodatkowe obliczenia dla transakcji. W zależności od liczby kont czas generowania raportu może się przynajmniej podwoić.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
