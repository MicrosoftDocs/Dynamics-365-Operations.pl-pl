---
title: Konfigurowanie ksiąg
description: Ten temat zawiera informacje dotyczące konfigurowania ksiąg poszczególnych osób prawnych. Zawiera on informacje o sposobach wybierania walut, kalendarzy obrachunkowych, planu kont oraz struktur kont, które powinny być używane z każdą z tych osób prawnych.
author: kweekley
ms.date: 09/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Ledger
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-09
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 38c4364c47915cc0019cb6b3d471d3e60d413bf0
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711556"
---
# <a name="configure-ledgers"></a>Konfigurowanie ksiąg

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje dotyczące konfigurowania ksiąg poszczególnych osób prawnych. Zawiera on informacje o sposobach wybierania walut, kalendarzy obrachunkowych, planu kont oraz struktur kont, które powinny być używane z każdą z tych osób prawnych.

## <a name="selecting-the-chart-of-accounts"></a>Wybieranie planu kont

Dla każdej osoby prawnej w Microsoft Dynamics 365 Finance należy skonfigurować szczegółowe informacje dotyczące księgi. Strona **Księga** umożliwia wybranie plan kont oraz struktur kont, które będą używane dla wybranej osoby prawnej. Plan kont i struktury kont można udostępniać, konfigurując korzystanie z tych samych planów kont i struktur kont na stronie **Księga** poszczególnych osób prawnych. Można również udostępnić część konfiguracji w każdej z osób prawnych i skonfigurować określone konfiguracje w każdej z osób prawnych.

Jeśli osoby prawne muszą mieć różne plany kont lub różne struktury kont, może być przydatna funkcja zastąpienia osoby prawnej. Korzystając z tych samych planów kont i struktur kont dla wielu osób prawnych, a następnie zarządzając wyjątkami poprzez zastępowanie osób prawnych, można z czasem uprościć konserwację.

Aby skonfigurować plan kont dla osoby prawnej, należy wybrać **Księga główna \> Ustawienia księgi głównej \> Księga**. Na stronie **Księga** wybierz **Plan kont**, a następnie wybierz z listy plan kont, który będzie używany. Należy zauważyć, że planu kont nie można zmienić po wybraniu wartości i zaksięgowaniu transakcji w osobie prawnej.

Aby uzyskać więcej informacji o planowaniu i konfigurowaniu planu kont i kont głównych, zapoznaj się z tematem [Planowanie planu kont](plan-chart-of-accounts.md).

## <a name="selecting-account-structures"></a>Wybieranie struktur konta

Każdą osobę prawną w Dynamics 365 Finance można skonfigurować w taki sposób, aby korzystała z jednej lub wielu struktur kont. Każda struktura konta określa wymiary finansowe oraz kombinacje kont głównych i wymiarów finansowych, które będą dozwolone podczas księgowania transakcji. Można stosować te same struktury kont w więcej niż jednej osobie prawnej.

Należy zauważyć, że jeśli istnieje wiele struktur kont, można wybrać tylko struktury kont, które nie mają nakładających się kombinacji kont głównych i wymiarów finansowych. Na przykład jedna ze struktur kont jest skonfigurowana w taki sposób, aby dodać jednostkę biznesową dla kont głównych z zakresu od 1000 do 1999. W innej strukturze konta dodano wymiar finansowy działu dla kont głównych rozpoczynających się od 1. W takim przypadku tylko jedna struktura konta może być dodana w tej samej osobie prawnej.

Aby skonfigurować struktury kont dla księgi, na stronie **Księga**, na skróconej karcie **Struktury kont** wybierz **Dodaj**, wybierz strukturę konta z listy, a następnie wybierz opcję **Wybierz**. Dodanie i zapisanie struktur kont może potrwać kilka minut. Należy zauważyć, że wybrane struktury kont muszą być aktywne. W przeciwnym razie szczegóły struktur kont nie będą obowiązywać w osobach prawnych, z którymi są połączone.

Aby usunąć strukturę konta, na stronie **Księga**, na skróconej karcie **Struktury konta** wybierz opcję **Usuń**. Należy zwrócić uwagę, że w przypadku usunięcia struktury konta z księgi nie zostaną usunięte wszystkie transakcje zaksięgowane przy użyciu konfiguracji tej struktury konta.

Aby uzyskać więcej informacji na temat konfigurowania struktur kont, należy zapoznać się z tematem [Konfigurowanie struktur kont](configure-account-structures.md).

## <a name="configuring-calendars-for-the-ledger"></a>Konfigurowanie kalendarzy dla księgi

Innym składnikiem księgi jest kalendarz obrachunkowy. Każda osoba prawna musi mieć wybrany kalendarz obrachunkowy. Można stosować ten sam kalendarz obrachunkowy w więcej niż jednej osobie prawnej. Po wybraniu kalendarza obrachunkowego w księdze zostanie wykonana kopia. Ta kopia jest określana jako kalendarz księgi. Kalendarz księgi umożliwia wybranie stanu okresów i modułów w poszczególnych okresach.

Aby uzyskać dostęp i zaktualizować kalendarz dla wybranej osoby prawnej, na stronie **Księga** w okienku akcji wybierz opcję **Kalendarz księgi**.

Aby wybrać kalendarz, wybierz **Kalendarze obrachunkowe**, a następnie wybierz kalendarz z listy. W przypadku zmiany kalendarza obrachunkowego po zaksięgowaniu transakcji w osobie prawnej należy wybrać opcję **Ponownie oblicz okresy księgi**. Następnie w wyświetlonym oknie dialogowym można zaktualizować salda księgi dla okresów w kalendarzu. Zaleca się, aby proces **Ponownie oblicz okresy księgi** uruchamiać w trybie **wsadowym** i w czasie, gdy w systemie są realizowane niekrytyczne procesy. W zależności od liczby transakcji i kombinacji wymiarów finansowych ten proces może potrwać trochę czasu.

Jeśli dla osoby prawnej nie wybrano kalendarza obrachunkowego, podczas próby zaksięgowania transakcji w tej osobie prawnej zostanie wyświetlony komunikat o błędzie.

Aby uzyskać więcej informacji, zobacz [Kalendarze, lata i okresy obrachunkowe](../budgeting/fiscal-calendars-fiscal-years-periods.md).

## <a name="using-a-balancing-financial-dimension"></a>Korzystanie z wymiaru finansowego bilansowania

Po wybraniu plan kont i dodaniu jednej lub kilku struktur konta można opcjonalnie wybrać jeden wymiar finansowy, który będzie używany jako wymiar finansowy bilansowania. Wybrany wymiar musi istnieć we wszystkich strukturach kont. Musi być również zbilansowany we wszystkich wpisach księgowych. Inaczej mówiąc, obciążenia i uznania muszą być takie same dla konta głównego i wymiaru finansowego bilansowania. System automatycznie tworzy transakcje w celu zbilansowania wpisów na podstawie kont głównych określonych w polach **Międzyjednostkowe — debet** i **Międzyjednostkowe — kredyt** na **stronie Konta dla transakcji automatycznych**.

Aby uzyskać więcej informacji na temat zapisów bilansowania, zobacz [Zbilansowane arkusze dla księgowania międzyjednostkowego](example-balanced-journals-interunit-accounting.md).

## <a name="configuring-currencies-for-the-ledger"></a>Konfigurowanie walut dla księgi

Strona **Księga** służy także do kontrolowania i definiowania walut, które będą używane podczas księgowania transakcji w księdze głównej. Należy określić walutę rozliczeniową, która jest walutą używaną w kolumnie **Waluta rozliczeniowa** w księdze głównej na wszystkich załącznikach. Ponadto w kolumnie **Waluta raportowania** można opcjonalnie wybrać drugą walutę. W przypadku wybrania waluty raportowania wszystkie transakcje będą rejestrowane w tej walucie w kolumnie **Waluta raportowania** w księdze głównej na wszystkich załącznikach.

Jeśli transakcje są księgowane w innej walucie, system automatycznie konwertuje kwotę transakcji z waluty transakcji na walutę rozliczeniową i walutę raportowania na załączniku. Na stronie **Księga** w polu **Typ kursu wymiany waluty rozliczeniowej** wybierz typ kursu wymiany skonfigurowany dla kursów wymiany, które powinny być używane do konwersji wartości z waluty transakcji na walutę rozliczeniową na załączniku. Jeśli wybrano walutę raportowania, należy również określić pole **Typ kursu wymiany waluty raportowania**, aby wskazać kurs wymiany, który ma być używany do konwersji wartości z waluty transakcji na walutę raportowania na załączniku.

W przypadku korzystania z funkcji budżetowania można również w polu **Typ kursu wymiany budżetu** określić kurs wymiany, który ma być używany do konwersji transakcji budżetowych z jednej waluty na inną.

W przypadku korzystania z dwóch walut lub w przypadku korzystania z jednej waluty, ale księgowania transakcji w innej walucie, należy skonfigurować skróconą kartę **Konta przeszacowania waluty** na stronie **Księga**. Na tej skróconej karcie definiuje się domyślne konta zrealizowanych i niezrealizowanych zysków i strat, które będą używane domyślnie podczas księgowania transakcji, jeśli na stronie **Konta przeszacowania waluty** nie określono konta. (Strona **Konta przeszacowania waluty** służy do konfigurowania różnych kont zrealizowanych i niezrealizowanych zysków i strat w poszczególnych walutach).

Zrealizowane zyski i straty to zyski i straty z zakończonych transakcji. Są one rejestrowane w zestawieniu zysków i strat. Niezrealizowane zyski i straty to zyski i straty, które się zmaterializowały, chociaż transakcja nie została dokonana. Oznacza to, że zaksięgowano na przykład fakturę, ale faktura nie została jeszcze rozliczona i zapłacona. Niezrealizowane zyski i straty są rejestrowane w bilansie.

Aby uzyskać więcej informacji na temat sposobu korzystania z dwóch walut, zobacz [Dwie waluty](dual-currency.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
