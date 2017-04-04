---
title: Konfigurowanie weksli
description: "W tym temacie opisano kroki dotyczące konfigurowania weksli."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269964
ms.assetid: f2077165-da90-4359-ab12-e05717728dc7
ms.search.region: global
ms.author: abruer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ce2142d946085d8bfc577accf1bb31a89ea29156
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bills-of-exchange"></a>Konfigurowanie weksli

W tym temacie opisano kroki dotyczące konfigurowania weksli.

Weksel to pisemne lub elektroniczne oświadczenie odbiorcy określająca innej strony, zwykle bank, powinni zapłacić określoną kwotę do firmy. Gdy używasz weksla jako płatności za fakturę zamówienia sprzedaży lub fakturę niezależną, uznajesz konto klienta. Taki kredyt jest zabezpieczony wekslem do czasu, gdy klient zapłaci za weksel bankowi. Zazwyczaj będzie rozlicz fakturę za pomocą weksla w terminie płatności. Gdy otrzymasz powiadomienie z banku, że weksel został uznany, można zamknąć weksel. Weksel można narysować za pośrednictwem banku w jednej z następujących terminów:

-   W dniu, gdy przypada termin płatności. Takie podejście jest znany jako zakres kompetencji dla kolekcji.
-   Przed wyznaczonym terminem zazwyczaj dla daty rabatu określona w warunków płatności, które są ustawione dla odbiorcy. Podczas księgowania transakcji kwota rabatu jest księgowana na koncie wydatków. Pozostała kwota pozostaje zobowiązaniem dopóki bank nie otrzyma płatności od odbiorcy. Takie podejście jest znany jako zakres kompetencji dla rabatu.

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>Konfigurowanie profili księgowania dla weksla
Użyj **profilów księgowania odbiorców** stronę do księgowych profile korzystające z weksli, oprotestowania weksli, przekazy pieniężne dla kolekcji i przekazów dla rabatu. W **konto rozrachunkowe** wybierz Podsumowanie konta do księgowania kwot weksla. To konto jest przyznawane lub pobierane, w zależności od typu transakcji weksla:
-   Dla weksli to konto jest obciążane podczas księgowania weksli i po stronie kredytowej podczas księgowania przelewu dla rabatu lub przelewu dla kolekcji.
-   W przypadku oprotestowanych weksli, to konto jest obciążane, gdy zaksięgowany jest oprotestowany weksel.
-   W przypadku przekazów do odbioru, to konto jest obciążane, gdy zaksięgowany jest przekaz do odbioru.
-   W przypadku przekazów do dyskonta, to konto jest obciążane, gdy zaksięgowany jest przekaz do dyskonta.

W **konto rozliczeniowe** wybierz konto gotówkowe są księgowane kwoty weksla do. To konto jest obciążane w momencie rozliczenia weksla. W **przedpłaty podatku** wybierz konto rozrachunkowe do księgowania kwot podatku do kiedy weksle są używane dla przedpłat. W **konto pasywów dla rabatów** wybierz konto do księgowania kwoty rabatu dla przekazów dla rabatu. To konto jest tworzone, gdy zostaje zaksięgowany przekaz do dyskonta.

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>Konfigurowanie kont z odbiorcami Parametry dla weksli
Na **rozrachunków z odbiorcami Parametry** strona domyślna profilów księgowania dla weksli są wprowadzane w **Księga i podatek** kartę. Sekwencje numerów są definiowane na **Number sequences** kartę.
Konfigurowanie nazw arkuszy dla weksla
------------------------------------------

Na **nazwy arkuszy** stronie, Utwórz co najmniej pięć nazw arkuszy służących do weksli. Oto typy arkuszy:
-   **Weksel odbiorcy** — umożliwia utworzenie nazwy arkusza dla arkusza wystawiania weksli.
-   **Oprotestowany weksel odbiorcy** — umożliwia utworzenie nazwy arkusza dla arkusza oprotestowania weksli.
-   **Ponownego wystawiania weksli odbiorców** — umożliwia utworzenie nazwy arkusza dla arkusza ponownego wystawiania weksli.
-   **Przelew bankowy odbiorcy** — umożliwia utworzenie nazwy arkusza dla arkusza spłaty.
-   **Rozlicz weksel odbiorcy** — umożliwia utworzenie nazwy arkusza dla arkusza rozliczania weksli.

Na stronie Załącznik arkusza dla każdego arkusza weksli, wprowadź informacje o wekslu **weksli** kartę. Po zaksięgowaniu wierszy arkusza weksli, można je przeglądać na **zapytania dotyczącego arkusza weksli** stronę i **statystyk weksli** strony.
Konfiguracja metod płatności dla weksli
-----------------------------------------------

Na **metody płatności** strony, skonfigurować co najmniej jedną metodę płatności dla weksli. Jeśli firma prowadzi wymianę handlową z więcej niż jednego banku, skonfigurować metodę płatności, który odpowiada format przekazu, który każdy bank wymaga weksli.
Konfigurowanie opłat od płatności dla weksla
-----------------------------------------

Opłata od płatności to opłata, która jest skojarzona z procesem zbierania płatności od odbiorców. Wiele ustawienia opłat płatności, które linie mogą być skojarzone każda opłata od płatności. Wiersze ustawień służy do określania sposobu obliczania kwoty domyślnej dla opłat. Można na przykład utworzyć wiersze ustawień dla metod płatności, specyfikacji płatności, walut i okresów. Można również utworzyć wiersze ustawień dla procent lub kwota, który jest oparty na sześćdziesięciu dni. Na przykład można skonfigurować wartości procentowej odsetek, który jest oparty na czas, który jest zaległe płatności. Jeśli bank pobiera różne opłaty za różne typy przekazów takich jak **kolekcji** lub **rabatu**, zdefiniować wiersz osobną płatność opłaty dla każdego typu przekazu.
Konfiguracja opłaty za przekaz dla plików przekazu bankowego
------------------------------------------------

Na **kont bankowych** stronę, można skonfigurować opłat za przekazy, które bank opłat dla każdego pliku przekazu, który jest generowany. Opłaty za przekaz są księgowane, gdy przekaz zostanie potwierdzony i gdy znana jest kwota zrealizowanej opłaty. Opłat za przekazy różnią się od opłat, które są zbierane od klientów i dołączone do wierszy arkusza.
Konfigurowanie układów dokumentu dla weksla
---------------------------------------------

Na **kont bankowych** kliknij przycisk **skonfigurować**i określić układ dokumentu, która jest wymagana dla każdego konta bankowego wygeneruje drukowanych weksli dokumentów dla.
Konfigurowanie klientów dla weksli
--------------------------------------

Na **klienci** strona, dla każdego klienta, który zgodził się zapłacić za pomocą weksli, można skonfigurować domyślną metodę płatności dla weksli na **ustawienia domyślne płatności** kartę.




