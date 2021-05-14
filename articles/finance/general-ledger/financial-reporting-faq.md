---
title: Raportowanie finansowe — często zadawane pytania
description: W tym temacie omówiono pytania związane z raportowaniem finansowym zgłoszone przez innych użytkowników.
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
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923032"
---
# <a name="financial-reporting-faq"></a>Raportowanie finansowe — często zadawane pytania 

Ten temat zawiera odpowiedzi na często zadawane pytania dotyczące raportowania finansowego. 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>Jak ograniczyć dostęp do raportu przy użyciu zabezpieczeń drzewa?

Na poniższym przykładzie pokazano, jak ograniczyć dostęp do raportu przy użyciu zabezpieczeń drzewa.

Firma demonstracyjna USMF ma raport bilansowy, do którego nie wszyscy użytkownicy raportowania finansowego powinni mieć dostęp. W celu ograniczenia dostępu do jednego raportu można użyć zabezpieczenia drzewa, dzięki któremu dostęp do raportu będą mieć tylko wybrani użytkownicy. Aby ograniczyć dostęp, należy wykonać następujące kroki: 

1. Zaloguj się do projektanta Financial Reporter Report Designer.
2. Utwórz nową definicję drzewa. Przejdź do opcji **Plik > Nowy > Definicja drzewa**.
3. Kliknij dwukrotnie wiersz **Podsumowanie** w kolumnie **Zabezpieczenia jednostki**.
4. Wybierz opcję **Użytkownicy i grupy**.  
5. Wybierz użytkowników lub grupy, które wymagają dostępu do tego raportu. 
6. Wybierz opcję **Zapisz**.
7. W definicji raportu dodaj nową definicję drzewa.
8. W definicji drzewa wybierz opcję **Ustawienie**. W obszarze **Wybór jednostki raportowania** wybierz opcję **Uwzględnij wszystkie jednostki**.

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a>Jak określić, które konta nie pasują do moich sald?

Jeśli masz raport, który nie zawiera pasujących sald, wykonaj kilka kroków w celu zidentyfikowania każdego z tych kont oraz odchyleń. 

**Financial Reporter Report Designer**
1. W projektancie Financial Reporter Report Designer utwórz nową definicję wiersza. 
2. Kliknij opcję **Edycja > Wstaw wiersze z wymiarów**.
3. Wybierz opcję **Konto główne**.  
4. Kliknij przycisk **OK**.
5. Zapisz definicję wiersza.
6. Utwórz nową definicję kolumny
7. Utwórz nową definicję raportu.
8. Wybierz opcję **Ustawienia** i usuń jej zaznaczenie.  
9. Wygeneruj raport. 
10. Wyeksportuj raport do programu Microsoft Excel.

**Dynamics 365 Finance** 
1. W rozwiązaniu Dynamics 365 Finance przejdź do opcji **Księga główna > Zapytania i raporty > Bilans próbny**.
2. Ustaw następujące parametry:
   - **Data początkowa** — wprowadź początek roku obrachunkowego.
   - **Data końcowa** — wprowadź datę generowania raportu.
   - **Wymiar finansowy** — ustaw wartość tego pola na **Ustawione konto główne**.
 3. Wybierz pozycję **Oblicz**.
 4. Wyeksportuj raport do programu Microsoft Excel.

Teraz powinno być możliwe skopiowanie danych z raportu raportowania finansowego w programie Excel do raportu bilansu próbnego, by można było porównać kolumny **Saldo zamknięcia**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]