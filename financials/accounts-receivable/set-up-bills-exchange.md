---
title: Konfigurowanie weksli
description: W tym temacie opisano kroki konfigurowania weksli.
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

[!include[banner](../includes/banner.md)]


W tym temacie opisano kroki konfigurowania weksli.

Weksel jest pisemnym lub elektronicznym oświadczeniem odbiorcy, które określa, że inna strona, zwykle bank, powinna zapłacić firmie określoną kwotę. Gdy używasz weksla jako płatności za fakturę zamówienia sprzedaży lub fakturę niezależną, uznajesz konto klienta. Taki kredyt jest zabezpieczony wekslem do czasu, gdy klient zapłaci za weksel bankowi. Z reguły faktura jest rozliczana wekslem w terminie płatności. Gdy otrzymasz powiadomienie z banku, że weksel został uznany, można zamknąć weksel. Weksel można wystawiać przez swój bank w dowolnym z następujących momentów:

-   W dniu, gdy przypada termin płatności. Taka metoda jest znana jako przekazanie do zapłaty.
-   Przed terminem płatności, zazwyczaj w terminie rabatu określonym przez warunki płatności ustalone dla odbiorcy. Podczas księgowania transakcji kwota rabatu jest księgowana na koncie wydatków. Pozostała kwota pozostaje zobowiązaniem dopóki bank nie otrzyma płatności od odbiorcy. Taka metoda jest znana jako przekazanie do dyskonta.

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>Konfigurowanie profili księgowania dla weksla
Na stronie **Profile księgowania odbiorców** można skonfigurować profile księgowania, których można używać do obsługi weksli, oprotestowania weksli, przekazywania do zapłaty i przekazywania do dyskonta. W polu **Konto rozrachunkowe** wybierz konto rozrachunkowe, na którym będą księgowane kwoty weksli. Księgowanie na tym koncie odbywa się po stronie debetowej lub kredytowej, w zależności od typu transakcji wekslowej:
-   W przypadku weksli to konto jest obciążane, gdy weksel jest księgowany, a uznawane, gdy jest księgowane przekazanie do dyskonta lub przekazanie do zapłaty.
-   W przypadku oprotestowanych weksli, to konto jest obciążane, gdy zaksięgowany jest oprotestowany weksel.
-   W przypadku przekazów do odbioru, to konto jest obciążane, gdy zaksięgowany jest przekaz do odbioru.
-   W przypadku przekazów do dyskonta, to konto jest obciążane, gdy zaksięgowany jest przekaz do dyskonta.

W polu **Konto rozliczeniowe** wybierz konto kasowe, na którym mają być księgowane kwoty weksli. To konto jest obciążane w momencie rozliczenia weksla. W polu **Przedpłaty podatku** wybierz konto rozrachunkowe, na którym mają być księgowane kwoty podatku, gdy weksle są używane dla przedpłat. W przypadku przekazywania do dyskonta w polu **Konto zobowiązań związanych z rabatami** wybierz konto, na którym mają być księgowane kwoty rabatów. To konto jest tworzone, gdy zostaje zaksięgowany przekaz do dyskonta.

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>Konfiguracja parametrów rozrachunków z odbiorcami dla weksli
Na stronie **Parametry modułu rozrachunków z odbiorcami** domyślne profile księgowania weksli wprowadza się na karcie **Księga i podatek**. Do ustawiania numeracji służy karta **Sekwencje identyfikatorów**.
Konfigurowanie nazw arkuszy dla weksla
------------------------------------------

Na stronie **Nazwy arkuszy** utwórz przynajmniej pięć nazw arkuszy do obsługi weksli. Oto dostępne typu arkuszy:
-   **Weksel wystawiony odbiorcy** — umożliwia utworzenie nazwy arkusza wystawiania weksli.
-   **Oprotestowany weksel odbiorcy** — umożliwia utworzenie nazwy arkusza oprotestowywania weksli.
-   **Ponownie wystawiony weksel odbiorcy** — umożliwia utworzenie nazwy arkusza ponownego wystawiania weksli.
-   **Przelew bankowy odbiorcy** — umożliwia utworzenie nazwy arkusza zapłaty weksli.
-   **Rozliczony weksel odbiorcy** — umożliwia utworzenie nazwy arkusza rozliczania weksli.

Na stronie załącznika arkusza dla każdego arkusza weksli wprowadź informacje o wekslu na karcie **Weksel**. Po zaksięgowaniu wierszy arkusza weksla można je wyświetlać na stronach **Zapytania o arkusz weksli** i **Statystyki weksli**.
Konfiguracja metod płatności dla weksli
-----------------------------------------------

Na stronie **Metody płatności** skonfiguruj co najmniej jedną metodę płatności weksli. Jeśli współpracujesz z więcej niż jednym bankiem, skonfiguruj metodę płatności, która odpowiada formatowi zapłaty weksla wymaganemu przez każdy bank.
Konfigurowanie opłat od płatności dla weksla
-----------------------------------------

Opłata od płatności to opłata, która jest skojarzona z procesem zbierania płatności od odbiorców. Z każdą opłatą od płatności można skojarzyć wiele wierszy ustawień opłat od płatności. Wiersze ustawień mogą służyć do kontrolowania sposobu obliczania kwot domyślnych opłat od płatności. Można na przykład utworzyć wiersze ustawień dla metod płatności, specyfikacji płatności, walut i okresów. Ponadto można utworzyć wiersze ustawień dla wartości procentowej lub kwoty na podstawie interwałów w dniach, na przykład wartości procentowej odsetek na podstawie okresu zaległych płatności. Jeśli bank nalicza różne opłaty dla różnych typów wypłaty, na przykład **Inkaso** lub **Rabat**, należy skonfigurować osobny wiersz opłaty od płatności dla każdego typu wypłaty.
Konfiguracja opłaty za przekaz dla plików przekazu bankowego
------------------------------------------------

Na stronie **Konta bankowe** można skonfigurować opłaty za przekazy, które są pobierane przez bank za każdy wygenerowany plik przekazu. Opłaty za przekaz są księgowane, gdy przekaz zostanie potwierdzony i gdy znana jest kwota zrealizowanej opłaty. Opłaty za przekazy różnią się od opłat za płatności, które są pobierane od odbiorców i dołączone do wierszy arkusza.
Konfigurowanie układów dokumentu dla weksla
---------------------------------------------

Na stronie **Konta bankowe** kliknij opcję **Konfiguracja** i określ układ dokumentu wymagany dla każdego konta bankowego, dla którego będą generowane drukowane dokumenty weksli.
Konfigurowanie klientów dla weksli
--------------------------------------

Na stronie **Odbiorcy** dla każdego odbiorcy, który zgodził się płacić za pomocą weksli, można skonfigurować domyślną metodę płatności weksli na karcie **Ustawienia domyślne płatności**.






