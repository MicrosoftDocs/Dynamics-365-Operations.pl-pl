---
title: Uzgadnianie konta bankowego
description: W tym temacie opisano sposób uzgadniania konta bankowego.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e9a9d1c53a4b9e764c1592cca898cd6f3293594
ms.sourcegitcommit: 299e20b59ebefa584ed46a13da3f1a7ff709e43c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2019
ms.locfileid: "1863639"
---
# <a name="reconcile-a-bank-account"></a>Uzgadnianie konta bankowego

[!include[banner](../includes/banner.md)]

Po otrzymaniu wyciągu bankowego należy okresowo uzgadniać transakcje bankowe podmiotu prawnego z transakcjami na wyciągu bankowym.

Nie można uzgodnić wyciągu z konta bankowego z kontem bankowym, jeśli którykolwiek z czeków lub płatności dokumentu wpłaty wymienionych w wyciągu ma stan **Anulowanie oczekujące**. Gdy osoba sprawdzająca zaksięguje lub odrzuci cofnięcie czeku lub anulowanie płatności dokumentu wpłaty, to stan nie będzie już miał wartości **Anulowanie oczekujące** i będzie można uzgodnić konto bankowe.

1.  Kliknij kolejno opcje **Zarządzanie gotówką i bankami** \> **Konta bankowe** \> **Konta bankowe**. Wybierz konto bankowe do uzgodnienia z wyciągu bankowego i wybierz **Uzgadnianie** > **Uzgadniania konta**.

2.  Wprowadź informacje w polach **Data wyciągu bankowego** i **Wyciąg bankowy**. W polu **Saldo końcowe** można wprowadzić saldo konta bankowego wskazane na wyciągu z konta bankowego.

3.  Wybierz opcję **Transakcje**, aby otworzyć stronę **Uzgadnianie konta**.

4.  W wypadku każdej transakcji zawartej w wyciągu bankowym zaznacz pole wyboru **Zaakceptowane**, jeśli kwota w Microsoft Dynamics 365 for Finance and Operations odpowiada kwocie na wyciągu bankowym. Można również wprowadzić lub zmodyfikować wartość w polu **Typ transakcji bankowej**. Ta wartość pola jest istotna ze względu na statystykę transakcji bankowych i niektóre raporty.
    

    > [!NOTE]
    > <P>Nie zaznaczaj pola wyboru <STRONG>Zaakceptowane</STRONG> w wypadku transakcji nieuwzględnionych w wyciągu bankowym. Transakcje te nadal będą wyświetlane na tej stronie aż do momentu, gdy zostaną uzgodnione z przyszłym wyciągiem bankowym.</P>
    > <P>Pole wyboru <STRONG>Zaakceptowane</STRONG> jest niedostępne, jeśli transakcja ma stan <STRONG>Anulowanie oczekujące</STRONG>. Transakcje mogą przybierać ten stan, jeśli w programie Finance and Operations skonfigurowano opcję, zgodnie z którą operacje stornowania lub anulowania muszą przed zaksięgowaniem zostać skierowane do weryfikacji. Gdy osoba sprawdzająca zaksięguje lub odrzuci cofnięcie, to stan nie będzie już miał wartości <STRONG>Anulowanie oczekujące</STRONG> i będzie można uzgodnić konto bankowe z wyciągiem bankowym.</P>

    
    Aby zaznaczyć pole wyboru **Zaakceptowane**dla interwału sprawdzania, czy wszystko jest wyświetlane na wyciągu bankowym, wybierz opcję **Zaznacz zakres sprawdzania**, a następnie wskaż interwał.

5.  Jeśli kwota dla transakcji na koncie bankowym nie odpowiada kwocie dla transakcji na wyciągu bankowym, wprowadź kwotę korekty w polu **Kwota korekty**.
    

    > [!NOTE]
    > <P>Jeśli okres obrachunkowy korygowanej transakcji jest zamknięty, pole <STRONG>Kwota korekty</STRONG> nie może być użyte. Trzeba wtedy utworzyć wiersz z datą transakcji przypadającą w otwartym okresie obrachunkowym, w którym można wprowadzać poprawki. W takim przypadku należy dodać wymiary finansowe, które były używane w oryginalnej transakcji, a także przesunięcie konta głównego.</P>



6.  Utwórz transakcje dla wpisów (na przykład opłat i odsetek) występujących w wyciągu z konta bankowego, lecz nie zarejestrowanych w systemie Finance and Operations. Wprowadź **Typ transakcji bankowej** i odpowiednie wymiary finansowe.

7.  Gdy transakcje są oznaczane w wyciągu z konta bankowego jako**Zaakceptowano**, pole **Nieuzgodnione** (którego zawartość jest ponownie obliczana po wprowadzeniu jakiejś zmiany) przyjmuje wartość coraz bliższą zeru. Gdy wartość będzie równa 0, kliknij opcję **Uzgodnienie konta**, aby zaksięgować uzgodnienie oraz transakcje i wprowadzone poprawki.
    
    Uwzględnionych transakcji nie można modyfikować ani korygować po zaksięgowaniu uzgodnień. Nie są one także wyświetlane podczas uzgadniania konta w przyszłości.

8.  Aby wyświetlić transakcje bankowe, które nie zostały jeszcze uzgodnione, należy użyć raportu **Nieuzgodnione transakcje bankowe**. Aby wyświetlić wyciąg bankowy dla konta bankowego, należy użyć raportu **Wyciąg bankowy**.

# <a name="cancel-bank-statement-reconciliation"></a>Anuluj uzgodnienie wyciągu bankowego 

Funkcja Anuluj uzgodnienie wyciągu bankowego umożliwia anulowanie uzgodnienia wyciągu bankowego. Aby użyć tej funkcji, należy włączyć funkcję **Anuluj uzgadnianie wyciągu bankowego** w obszarze roboczym **Zarządzanie funkcjami**. Należy również włączyć parametr **Zezwalaj na edycję wyciągu bankowego**. W tym celu przejdź do **Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami > Uzgadnianie konta bankowego**.
 
Rozliczenia wyciągu bankowego można anulować tylko w porządku chronologicznym, w którym zostały wprowadzone. Gdy uzgodnienie wyciągu bankowego zostanie anulowane, nowe transakcje i korekty zostaną wycofane, a wszystkie inne transakcje zostaną oznaczone jako nieuzgodnione.
 
Aby anulować uzgadnianie wyciągu bankowego, wybierz wyciąg bankowy i wybierz **Wyciąg bankowy > Anuluj uzgodnienie konta bankowego**. Na stronie **Anulowanie uzgodnienia konta bankowego** podaj **kod przyczyny**, **komentarz przyczyny** oraz **datę anulowania**. Wybierz **OK**, aby rozpocząć anulowanie. Uwaga: data anulowania wyciągu bankowego musi być w dniu lub po dacie wyciągu bankowego. Po anulowaniu rozliczenia wyciągu bankowego pole **Data anulowania** dla wyciągu bankowego zostanie zaktualizowane o podany **termin anulowania**. Wybierz przycisk **Transakcje**, aby wyświetlić transakcje, dla których uzgodnienie zostało anulowane.
