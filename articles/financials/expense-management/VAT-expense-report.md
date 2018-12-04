---
title: "Zwrot podatku VAT w module Zarządzanie wydatkami"
description: "W tym temacie wyjaśniono, jak otrzymywać zwroty z kwalifikujących się transakcji zawierających podatek od towarów i usług (VAT)."
author: saraschi2
manager: AnnBe
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvPerDiems
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: d1c9357f8f51e1a87aebeb8f802dbe3b5fdd5aa0
ms.contentlocale: pl-pl
ms.lasthandoff: 03/13/2018

---

# <a name="vat-recovery-in-expense-management"></a>Zwrot podatku VAT w module Zarządzanie wydatkami

[!include [banner](../includes/banner.md)]

Aby otrzymywać zwroty od kwalifikujących się transakcji zawierających podatek od towarów i usług (VAT), firma lub organizacja musi identyfikować, gromadzić, weryfikować i przesyłać określone precyzyjne informacje. Ten proces obejmuje wiele zadań, a zależnie od wielkości firmy może angażować wielu pracowników lub ról.

Aby odzyskiwać podatek VAT za pomocą modułu Zarządzanie wydatkami, muszą być spełnione następujące wymagania wstępne:

- Muszą być utworzone kody podatków dla krajów/regionów, które są przydzielone do kategorii wydatków.
- Dla każdego kodu podatku należy utworzyć grupę podatków.
- Dla każdej grupy podatków należy utworzyć kod podatku dla pozycji.

Po spełnieniu wymagań wstępnych pracownicy muszą wykonać następujące kroki, aby wnioskować o zwrot z transakcji zawierających podatek VAT.

1. W raporcie z wydatków wprowadzenie informacji podatkowych dotyczących transakcji kartami kredytowymi, aby zidentyfikować kwalifikujące się zwroty podatku VAT.
2. Upewnienie się, że wszystkie informacje podatkowe są kompletne, a następnie zaksięgowanie raportu z wydatków.
3. Przetwarzanie wydatków kwalifikujących się do zwrotu podatku VAT z transakcji zagranicznych.
4. Wysłanie danych zwrotu podatku VAT do zewnętrznego dostawcy, który złoży wnioski o zwrot z tytułu transakcji międzynarodowych.
5. Przetwarzanie wydatków do zwrotu podatku VAT z transakcji krajowych.

W poniższych sekcjach przedstawiono przykłady pokazujące, jak pracownicy firmy Contoso realizują każdy krok.

## <a name="on-an-expense-report-enter-tax-information-about-credit-card-transactions-to-identify-eligible-vat-refunds"></a>W raporcie z wydatków wprowadzenie informacji podatkowych dotyczących transakcji kartami kredytowymi, aby zidentyfikować kwalifikujące się zwroty podatku VAT

Nancy, przedstawiciel handlowy firmy Contoso zatrudniony w Stanach Zjednoczonych, niedawno wróciła z wyjazdu służbowego do Wielkiej Brytanii. Podczas wjazdu opłacała posiłki z prywatnej karty kredytowej. Teraz musi sporządzić raport wydatków w celu uzgodnienia poniesionych wydatków.

Wprowadzając informacje w raporcie z wydatków, Nancy wybiera pozycję **Wielka Brytania** w polu **Kraj/region** na stronie **Edytuj raport z wydatków**. Lista grup podatków zostanie wyfiltrowana i pokaże tylko grupy mające zastosowanie do Wielkiej Brytanii. Nancy wybiera grupę podatków **Wielka Brytania 001**, a następnie wybiera grupę podatków dla pozycji **Posiłki**. Następnie dodaje nową transakcję dotyczącą zakwaterowania. Ponieważ w Wielkiej Brytanii w odniesieniu do zakwaterowania istnieje tylko jedna grupa podatków i jedna grupa podatków dla pozycji, te informacje są wstawiane automatycznie do raportu z wydatków sporządzanego przez Nancy.

Zgodnie z polityką Contoso wszystkie wydatki muszą być potwierdzone paragonami. W związku z tym gdy Nancy zapisuje raport z wydatków, otrzymuje komunikat informujący, że musi dołączyć paragon dla każdej transakcji wyszczególnionej w raporcie. Nancy sprawdza, czy do raportu z wydatków dołączyła cyfrowy obraz paragonu każdej transakcji, a następnie przesyła raport do zatwierdzenia. Następnie wysyła papierowe paragony w zespołu zajmującego się przetwarzaniem na zapleczu. Ten zespół wyśle dane zwrotu podatku VAT do zewnętrznego dostawcy, który w imieniu Contoso złoży wnioski o zwrot podatku VAT z tytułu transakcji międzynarodowych.

## <a name="make-sure-that-all-tax-information-is-complete-and-then-post-the-expense-report"></a>Upewnienie się, że wszystkie informacje podatkowe są kompletne, a następnie zaksięgowanie raportu z wydatków

April, koordynatorka rozrachunków z dostawcami w Contoso, musi wprowadzić wszelkie informacje o podatkach brakujące w raporcie z wydatków, zanim będzie można zaksięgować raport. Otwiera stronę **Szczegółowe informacje o raporcie z wydatków** i widzi zatwierdzony raport z wydatków Nancy. Następnie otwiera raport w celu przejrzenia szczegółów transakcji. Widzi, że Nancy nie wprowadziła grupy podatków dla pozycji dla jednej transakcji. Z powoduj braku tej informacji April nie może zaksięgować raportu z wydatków. Z tego względu April spogląda na stronę **Konfiguracje podatku** w module Zarządzanie wydatkami i wyszukuje grupę podatków dla pozycji odpowiednią dla kraju/regionu i typu transakcji. Teraz April może zaksięgować raport z wydatków w księdze głównej.

Gdy April księguje raport z wydatków, jest tworzony element pracy dotyczący zwrotu podatku VAT. Ten element pracy jest przypisywany do członka zespołu zajmującego się przetwarzaniem na zapleczu. April otrzymuje komunikat potwierdzający, że księgowanie zakończyło się pomyślnie. Ten komunikat podaje również liczbę transakcji z podatkiem VAT, które zostały zidentyfikowane dla zwrotu.

## <a name="process-expenses-that-are-eligible-for-international-vat-recovery"></a>Przetwarzanie wydatków kwalifikujących się do zwrotu podatku VAT z transakcji zagranicznych

Arnie, członek zespołu przetwarzania na zapleczu w Contoso, jest odpowiedzialny za potwierdzenie, że wszystkie informacje niezbędne do zwrotu podatku VAT są uwzględnione w raporcie z wydatków. Otwiera stronę **Zwrot podatku od wydatków** i wybiera raport z wydatków przesłany przez Nancy. Arnie sprawdza, czy dołączono wszystkie wymagane paragony oraz wprowadzono poprawne grupę podatków i kody podatków dla pozycji.

Po otrzymaniu papierowych paragonów od Nancy Arnie porównuje je z paragonami cyfrowymi, a następnie zmienia stan raportu z wydatków na **Gotowy do zwrotu**.

## <a name="send-vat-recovery-data-to-the-third-party-vendor-to-file-international-recovery-returns"></a>Wysłanie danych zwrotu podatku VAT do zewnętrznego dostawcy, który złoży wnioski o zwrot z tytułu transakcji międzynarodowych

Gdy Arnie jest gotowy do wysłania danych z raportu wydatków do zewnętrznego dostawcy, który złoży wnioski o zwrot podatku VAT, otwiera strony **Zwrot podatku od wydatków**. Filtruje stronę, tak aby widzieć tylko raporty z wydatków oznaczone statusem **Gotowy do zwrotu**. Następnie Arnie wybiera kolejno opcje **Plik** &gt; **Eksportuj do programu Excel**. Informacje o podatku VAT z raportów z wydatków są eksportowane do arkusza programu Microsoft Excel. Arnie przesyła ten arkusz do zewnętrznego dostawcy i dołącza wiadomość informującą, że paragony papierowe zostały wysłane kurierem.

## <a name="process-expenses-for-domestic-vat-recovery"></a>Przetwarzanie wydatków do zwrotu podatku VAT z transakcji krajowych

Arnie musi sprawdzić, czy transakcje w raportach z wydatków kwalifikują się do zwrotu podatku VAT oraz czy do raportów dołączono cyfrowe paragony. Aby rozpocząć przetwarzanie wydatków za transakcje krajowe kwalifikujących się do zwrotu podatku, Arnie otwiera stronę **Zwrot podatku od wydatków** i wybiera raport z wydatków wymagający weryfikacji. Sprawdza, czy paragony są wystawione na nazwę firmy, a nie imię i nazwisko pracownika. Aby otrzymać zwrot podatku VAT, paragony muszą być wystawione na firmę. Arnie następnie sprawdza, czy zastosowano poprawne grupę podatków i kody podatków dla pozycji.

Gdy Arnie otrzymuje paragony papierowe, zmienia stan raportu z wydatków na **Gotowy do zwrotu**. Może wtedy złożyć wniosek o zwrot do odpowiedniego organu skarbowego. W tym przypadku właściwym organem skarbowym w Stanach Zjednoczonych jest Internal Revenue Service (IRS).

