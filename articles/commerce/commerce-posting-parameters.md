---
title: Parametry księgowania rozwiązania Commerce
description: Ten artykuł opisuje parametry, które są specyficzne dla księgowania transakcji finansowych i fizycznych w Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: 56a2d1d2bcafdcdd9d88c132986e8ef485bf6b24
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027235"
---
# <a name="commerce-posting-parameters"></a>Parametry księgowania rozwiązania Commerce

[!include [banner](includes/banner.md)]

Ten artykuł opisuje parametry, które są specyficzne dla księgowania transakcji finansowych i fizycznych w Microsoft Dynamics 365 Commerce. Parametry delegowania Commerce znajdują się w centrali Commerce na stronie **Retail i Commerce \> Ustawienia centrali \> Parametry \> Parametry Commerce \> Delegowanie**.

## <a name="periodic-discount-parameters"></a>Parametry rabatu okresowego

Poniższa tabela przedstawia parametry rabatu okresowego, które są specyficzne dla księgowania transakcji finansowych i fizycznych.

| Parametr | Opis |
|-----------|-------------|
| Księguj rabat okresowy | Ta opcja decyduje o tym, czy oferty okresowe są księgowane na kontach księgi głównej. Rabaty okresowe obejmują rabaty łączone, ilościowe i oferty z rabatem. Gdy ten parametr jest włączony, w sekcji **Zniżki okresowe** można ustawić dodatkowe pola. |
| Typ konta księgowego | <p>Wybierz typ konta, które jest używane do księgowania zniżek okresowych:</p><ul><li>**Standard** – system nie używa pól związanych z rabatem na tej stronie. Zamiast tego używa kont zdefiniowanych na stronie **Ksiegowanie** w centrali Commerce (**Zarządzanie zapasami \> Konfiguracja \> Księgowanie \> Formularze księgowania**).</li><li>**Okresowo** – system używa kont rabatowych Commerce, które są określone przez pola dotyczące rabatów na tej stronie. Jeśli wybierzesz tę opcję, musisz określić konto księgi głównej (GL) dla każdego typu oferty (rabat, rabat łączony, ilość i próg). Podczas konfigurowania każdej zniżki możesz zdefiniować konto. Kiedy na stronie konfiguracji rabatu używana jest funkcja księgowania na koncie rabatowym, dokonywany jest dodatkowy wpis debetowy i kredytowy, aby przeklasyfikować księgowanie rabatu z konta GL rabatu Commerce na konto GL rabatu. Aby uzyskać więcej informacji, zobacz [Rabaty Retail](retail-discounts-overview.md).</li></ul> |
| Kod rabatowy informacji księgowania | Ta opcja nie jest już używana w standardowym rozwiązaniu Commerce i zostanie wycofana. |
| Księguj rabat okresowy dla zamówień | Ta opcja kontroluje, czy okresowe rabaty detaliczne są księgowane w księgach rachunkowych dla zamówień klientów i zamówień centrum. |

## <a name="inventory-update-parameters"></a>Parametry aktualizacji zapasów

Poniższa tabela przedstawia parametry aktualizacji zapasów, które są specyficzne dla księgowania transakcji finansowych i fizycznych.

| Parametr | Opis |
|-----------|-------------|
| W razie nieznalezienia numerów partii używaj domyślnego identyfikatora partii | Ta opcja kontroluje, czy domyślny identyfikator partii jest używany dla pozycji z włączoną obsługą partii, jeśli nie znaleziono numerów partii, a dozwolona jest ujemna inwentaryzacja. |
| Domyślny identyfikator partii | Numer partii, którego należy użyć, jeśli nie znaleziono numerów partii dla przedmiotów, a parametr **Użyj domyślnego identyfikatora partii, gdy nie znaleziono numerów partii** jest włączony. |

## <a name="aggregation-parameters"></a>Parametry agregacji

Poniższa tabela przedstawia parametry agregacji zapasów, które są specyficzne dla księgowania transakcji finansowych i fizycznych.

| Parametr | Opis |
|-----------|-------------|
| Przekaż pieniądze do sejfu | Włączenie tego parametru powoduje agregowanie wszystkich transakcji podczas księgowania zestawienia i tworzenie jednego wiersza w dzienniku do księgowania zamiast osobnego wiersza dla każdego zrzutu. |
| Przekazanie pieniędzy do banku | Włączenie tego parametru powoduje agregowanie wszystkich transakcji podczas księgowania zestawienia i tworzenie jednego wiersza w dzienniku do księgowania zamiast osobnego wiersza dla każdego zrzutu. |
| Transakcje sprzedaży | Włącz ten parametr, aby skonsolidować transakcje w ramach procesu księgowania zestawienia transakcji. Zalecamy, abyś włączył ten parametr. Wcześniej nosiła nazwę **Transakcje voucherowe**. |
| Nie agreguj zwrotów | po wybraniu tej opcji każda transakcja zwrotu zostanie zaksięgowana jako osobne zlecenie sprzedaży podczas księgowania zestawienia detalicznego. |

## <a name="batch-processing-parameters"></a>Parametry przetwarzania wsadowego

Poniższa tabela zawiera listę parametrów przetwarzania wsadowego, które są specyficzne dla księgowania transakcji finansowych i fizycznych.

| Parametr | Opis |
|-----------|-------------|
| Maksymalna liczba wyrażeń równoległych | To pole określa liczbę zadań wsadowych, które są używane do księgowania wielu wyciągów. |
| Maksymalna liczba wątków do przetwarzania zamówień z jednego zamówienia | To pole reprezentuje maksymalną liczbę wątków używanych przez zadanie wsadowe księgowania zestawienia do tworzenia i fakturowania zamówień sprzedaży dla jednego zestawienia. Całkowita liczba wątków, z których korzysta proces wysyłania zestawień, jest obliczana przez pomnożenie wartości tego parametru przez wartość parametru **Maksymalna liczba równoległych wysyłek zestawień**. Ustawienie zbyt dużej wartości tego parametru może mieć negatywny wpływ na wydajność procesu księgowania zestawienia. |
| Maksymalna liczba wierszy transakcji w agregacji | To pole określa liczbę wierszy transakcji, które zostaną uwzględnione w jednej zagregowanej transakcji przed utworzeniem nowej. Zagregowane transakcje są tworzone na podstawie różnych kryteriów agregacji, takich jak odbiorca, Data firmy lub wymiary finansowe. Należy pamiętać, że wiersze z pojedynczej transakcji nie będą dzielone między różne zagregowane transakcje. Tak więc istnieje możliwość, że liczba wierszy w zagregowanej transakcji jest nieco wyższa lub niższa w zależności od czynników, takich jak liczba odrębnych produktów. |
| Maksymalna liczba wątków sprawdzania poprawność transakcji w sklepie | To pole definiuje maksymalną liczbę wątków używanych do walidacji transakcji. Walidacja transakcji jest wymaganym krokiem, który musi nastąpić, zanim transakcje zostaną włączone do zestawień. Musisz także zdefiniować produkt w postaci karty podarunkowej na skróconej karcie **Karta podarunkowa** w zakładce **Księgowanie** na stronie **Parametry handlowe**, nawet jeśli organizacja nie używa kart podarunkowych. |

W poniższej tabeli podano zalecane wartości parametrów z poprzedniej tabeli. Wartości te powinny być przetestowane i dopasowane do konfiguracji wdrożenia oraz dostępnej infrastruktury. Wartości przekraczające wartości zalecane mogą mieć negatywny wpływ na inne procesy wsadowe i powinny być poddane walidacji.

| Parametr | Zalecana wartość | Szczegóły |
|-----------|-------------------|---------|
| Maksymalna liczba równoległych operacji księgowania zestawień | <p>Umożliwia ustawienie tego parametru na liczbę zadań wsadowych dostępnych dla grupy zadań wsadowych, w których jest uruchomione zadanie **Zestawienia**.</p><p>**Reguła ogólna:** Pomnóż liczbę serwerów wirtualnych serwera obiektów aplikacji (AOS) przez liczbę zadań wsadowych dostępnych na serwerze wirtualnym AOS.</p> | Ten parametr nie ma zastosowania, gdy włączona jest funkcja **Zestawienia detaliczne – podawanie kroplowe**. |
| Maksymalna liczba wątków do przetwarzania zamówień z jednego zamówienia | Rozpocznij od wartości testowych o wartości **4**. Zwykle wartość nie powinna przekraczać **8**. | Ten parametr określa liczbę wątków, które są używane do tworzenia i wysyłania zamówień sprzedaży. Reprezentuje on liczbę wątków, które są dostępne do wysłania w każdej wypowiedzi. |
| Maksymalna liczba wierszy transakcji w agregacji | Rozpocznij od wartości testowych o wartości **1000**. W zależności od konfiguracji centrali Commerce, mniejsze rozkazy mogą być bardziej korzystne dla wydajności. | Ten parametr określa liczbę wierszy, które będą zawarte w każdym zamówieniu sprzedaży podczas księgowania zestawienia. Po osiągnięciu tej liczby linie zostaną rozdzielone do nowego porządku. Liczba linii sprzedaży nie będzie dokładnie równa liczbie, którą podasz, ponieważ podział następuje na poziomie zamówienia sprzedaży. Niemniej jednak liczba ta będzie zbliżona do liczby, która została ustawiona. Ten parametr jest używany do generowania zleceń sprzedaży dla transakcji detalicznych, które nie mają określonego klienta. |
| Maksymalna liczba wątków sprawdzania poprawność transakcji w sklepie | Zalecamy, abyś ustawił ten parametr na **4** i zwiększał go tylko wtedy, gdy nie osiągniesz zadowalającej wydajności. Liczba wątków, których używa ten proces, nie może przekroczyć liczby procesorów dostępnych dla serwera wsadowego. Jeśli liczba wątków jest zbyt duża, może to mieć wpływ na inne przetwarzanie wsadowe. | Ten parametr kontroluje liczbę transakcji, które mogą być potwierdzane w tym samym czasie dla danego sklepu. |

> [!NOTE]
> Wszystkie ustawienia i parametry związane z księgowaniem zestawień, które są zdefiniowane w oknie Sklepy sieci sprzedaży i na stronie **Parametry rozwiązania Commerce**, mają zastosowanie do ulepszonej funkcji księgowania zestawień.

## <a name="invoice-parameters"></a>Parametry faktury

Poniższa tabela przedstawia parametry faktury, które są specyficzne dla księgowania transakcji finansowych i fizycznych.

| Parametr | Opis |
|-----------|-------------|
| Nazwa arkusza | Nazwa dziennika płatności, która jest używana, gdy tworzone są dzienniki płatności klienta dla płatności za zamówienia sprzedaży. To ustawienie dotyczy wszystkich płatności za zamówienia, które są księgowane w punktach sprzedaży (POS), centrum obsługi i kanałach e-commerce. |
| Nazwa konta | Nazwa rachunku płatniczego. |
| Określ priorytety wymiarów z formy płatności | Gdy ta flaga jest włączona, dzienniki płatności nadają priorytet wymiarom związanym z metodą płatności zamiast wymiarom związanym ze sklepem. |
| Zachowanie mechanizmu obliczania podatku | Ten parametr określa zachowanie, gdy zamówienia sprzedaży utworzone podczas księgowania zestawienia są fakturowane:<ul><li>**Oblicz ponownie** – ponownie oblicz podatki.</li><li> **Nie obliczaj ponownie** – użyj kwot podatku obliczonych w POS.</li></ul> |
| Nazwa arkusza | Nazwa dziennika, która jest używana, gdy tworzony jest dziennik płatności klienta dla zwrotów. To ustawienie dotyczy wszystkich płatności za zamówienia, które są księgowane w punktach sprzedaży (POS), centrum obsługi i kanałach e-commerce. |

## <a name="statement-parameters"></a>Parametry oświadczenia

Poniższa tabela przedstawia parametry oświadczenia, które są specyficzne dla księgowania transakcji finansowych i fizycznych.

| Parametr | Opis |
|-----------|-------------|
| Rezerwuj zapasy podczas obliczania | Gdy ten parametr jest włączony, obliczanie zestawienia tymczasowo rezerwuje zapasy do czasu zaksięgowania zestawienia. Ten parametr jest domyślnie wyłączony, aby poprawić wydajność obliczania zestawień. Uaktualnione informacje o stanie inwentarza można obliczyć za pomocą zadania wsadowego **Księgowanie zapasów**. Zwróć uwagę, że zadanie wsadowe **Księgowanie** inwentaryzacji nie jest już używane, gdy włączone jest tworzenie zamówień opartych na [podawanie stopniowe](trickle-feed.md) dla transakcji w sklepach detalicznych. |
| Wymagane wyłączenie zliczania | Ta flaga powoduje wyłączenie zliczania podczas księgowania w centrali Commerce. |
| Ponownie oblicz wymiary finansowe w razie błędu | Gdy ten parametr jest włączony, wymiary finansowe mogą być ponownie oceniane przy kolejnych księgowaniach zestawienia, jeśli księgowanie zestawienia nie powiedzie się. |
| Użyj wymiarów finansowych ze sklepu zwrotu | Kiedy ten parametr jest włączony, można tworzyć powiązane zlecenia sprzedaży zwrotnej, które używają wymiarów finansowych sklepu zamiast wymiarów finansowych z oryginalnej transakcji. |
| Odłącz zwroty | Gdy ten parametr jest włączony, zestawienie może tworzyć zwroty z nierozliczonej sprzedaży jako zwroty w ciemno. Ten parametr jest domyślnie wyłączony i zalecamy, byś go nie zmieniał. |
| Wyłącz księgowanie różnicy zaokrągleń | Ten parametr wyłącza księgowanie różnicy zaokrąglenia między płatnością za transakcję a kwotą brutto podczas przetwarzania płatności. |
| Automatyczne rozliczanie depozytów odbiorcy | Gdy ten parametr jest włączony, depozyty klientów, które są księgowane podczas księgowania zestawienia detalicznego, są rozliczane z otwartymi transakcjami klientów. |
| Włącz uzgadnianie zarządzania gotówką z punktu sprzedaży i użyj go | Gdy ten parametr jest włączony, uzgadnianie zarządzania gotówką odbywa się w POS, a wartości są przekazywane do księgowań detalicznych w celu utworzenia linii zestawienia. |
| Poziom szczegółowości vouchera księgi | Ten parametr określa poziom szczegółowości, jaki jest uwzględniany w kuponie księgi dla wybranych transakcji pochodzących z POS. Typy transakcji obejmują przychody, wydatki i rabaty. W przypadku zniżek parametr ten jest brany pod uwagę tylko wtedy, gdy numer konta dla zniżki okresowej i numer konta dla zniżki regularnej nie są takie same. Jeśli nie są wymagane szczegóły, **Podsumowanie** jest zalecaną wartością dla tych postów. Gdy zdefiniowane jest księgowanie na poziomie podsumowania, **TransactionDiscountTrans.RecID** nie będzie wypełniany. W wydaniu wersji Commerce 10.0.27 zmieniono nazwę tej flagi i przeniesiono ją. Wcześniej nosiła ona nazwę **Poziom szczegółowy** i znajdowała się w sekcji **Aktualizacja zapasów**. |
