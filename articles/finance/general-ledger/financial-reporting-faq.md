---
title: Raportowanie finansowe — często zadawane pytania
description: Ten temat zawiera odpowiedzi na niektóre często zadawane pytania dotyczące raportowania finansowego.
author: jiwo
ms.date: 01/13/2021
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
ms.openlocfilehash: e1b67f86446403933005008a9a1e2cc6739dc516
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266640"
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

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
