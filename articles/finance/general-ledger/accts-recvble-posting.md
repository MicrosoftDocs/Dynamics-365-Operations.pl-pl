---
title: Księgowanie rozrachunków z odbiorcami
description: Ten artykuł wyjaśnia, w jaki sposób konfiguruje się księgowania na kontach należności i podaje przykłady konfiguracji księgowań.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustPaymMode, CustCashDiscount, CommissionPosting, MarkupTable\_Cust, CustPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 492bbd31cae08a93cd68e5ce120d02a62141241b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874582"
---
# <a name="accounts-receivable-posting"></a>Księgowanie należności

[!include [banner](../includes/banner.md)]

Podstawowym profilem księgowania dla modułu **Należności** jest profil księgowania klienta. Ten profil księgowania określa konto podsumowujące używane podczas księgowania sald klienta w księdze głównej. Konto podsumowujące jest kontem głównym. Takie konto jest również nazywane kontem handlowym Należności.

Aby uzyskać więcej informacji, zobacz [Profile księgowania odbiorców](../accounts-receivable/customer-posting-profiles.md).

Poza profilem księgowania klienta w dziale Należności dostępnych jest kilka konfiguracji księgowania. Poniższe sekcje zawierają więcej informacji o tych innych konfiguracjach księgowania.

## <a name="posting-accounts-for-methods-of-payment"></a>Księgowanie kont dla metod płatności

Metody płatności określają sposób księgowania płatności w księdze głównej. Sterują one również zachowaniem danych wyjściowych płatności. Zazwyczaj tworzy się jedną metodę płatności dla każdego typu płatności akceptowanego przez twoją organizację (np. gotówka, czek, karta kredytowa, przekaz pieniężny, przelew).

Pola w sekcji **Księgowanie** na skróconej karcie **Ogólne** kontrolują sposób księgowania płatności w księdze głównej. Najpierw musisz wybrać wartość w **polu Typ konta**. Wybrane typ konta steruje działaniem pola **Konto płatności**. Zaleca się wybranie opcji **Bank** w polu **Typ konta**, a następnie wybranie konta bankowego w **polu Konto płatności**. Dzięki takiemu podejściu system będzie księgował płatność w poddarze Bank, które obsługuje uzgadnianie i inne procesy związane z gotówką. W poniższej tabeli pokazano przykład konfiguracji profilu księgowania, jeśli jest używasz modułu **Zarządzanie gotówką i bankami**.

| Typ księgowania | Typ konta | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Opis |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Bank | Bank | Bank of Contoso | Konto bankowe połączone ze środekem trwałym | Środki | Nie | Dla każdej metody płatności wprowadź konto główne w **polu Konto płatności**. |

Jeśli nie planujesz korzystania z funkcji zarządzania gotówką i bankami, wybierz opcję **Księga** w polu **Typ konta**, a następnie wybierz konto główne w polu **Konto płatności**. W poniższej tabeli przedstawiono przykład konfiguracji profilu księgowania, jeśli nie korzystasz z Zarządzania gotówką i bankami.

| Typ księgowania | Typ konta | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Opis |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Ledger | Ledger | 100100: Bank of Contoso | Element zawartości | Środki | Nie | Dla każdej metody płatności wprowadź konto główne w **polu Konto płatności**. |

## <a name="bridging-accounts"></a>Konta pomostowe

Księgowanie pomostowe to dwuetapowy proces, który jest używany podczas księgowania płatności. Jest to funkcja opcjonalna, która może być używana na przykład z kontami bankowymi z zerowym saldem. Zapewnia to bezproblemowy i bardziej terminowy proces uzgadniania konta bankowego. W pierwszym kroku płatność jest księgowana na koncie tymczasowym (koncie pomostowym). W drugim kroku zaksięgowany wpis jest wycofywny i księgowany na koncie bankowym, gdy bank je wyczyści. W poniższej tabeli pokazano przykład konfiguracji profilu księgowania dla księgowania pomostowego.

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Opis |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Arkusz księgi | 130725 | Gotówka niezrachiwowana | Pasywa | Uznanie | Tak | Dla każdej metody płatności wprowadź konto główne w **polu Konto pomostowe**. |

Aby uzyskać więcej informacji, zobacz [temat Konfigurowanie i przetwarzanie płatności pomostowych](../accounts-receivable/set-up-and-process-bridged-payments.md).

## <a name="posting-accounts-for-customer-cash-discounts"></a>Księgowanie kont dla rabatów gotówkowych klientów

Jeśli twoja organizacja oferuje klientom rabaty gotówkowe w zamian za szybką zapłatę, musisz skonfigurować kody rabatów gotówkowych i określić, w jaki sposób rabaty te powinny być księgowane w księdze głównej. Dostępnych jest kilka opcji określania konta głównego używanego do księgowania rabatu gotówkowego odbiorcy.

Aby uzyskać więcej informacji, zobacz [Rabaty gotówkowe](../cash-bank-management/cash-discounts.md).

## <a name="posting-accounts-for-payment-fees"></a>Księgowanie kont dla opłat za płatności

Opłaty umożliwiają automatyczne dodawanie opłaty do płatności klienta, jeśli obowiązuje zestaw warunków. Opłatami za płatności możesz obciążyć klienta lub mogą one zostać zaksięgowane na Twoim koncie bankowym jako koszt. Oto kilka przykładów:

- Pobierasz od klientów 3 procent od sumy płatności, jeśli płacą kartą kredytową.
- Opłaty bankowe są 1,00 $ za każdy przetwarzany przelew bankowy, a opłata jest naliczana wydatkowana.

Po skonfigurowaniu opłaty od płatności dla klienta, jeśli w polu **Opłata** zostanie ustawiona wartość **Klienta**, pole **Konto główne** stanie się niedostępne, a do zaksięgowania opłaty system użyje profilu księgowania klienta. Jeśli w polu **Opłata** zostanie ustawiona wartość **Księga**, należy ustawić pole **Konto główne** na koncie głównym, na którym zostanie zaksięgowana opłata od płatności. Zazwyczaj to konto główne będzie kontem wydatków. W poniższej tabeli przedstawiono przykład konfiguracji profilu księgowania dla księgowania opłat.

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Opis |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Arkusz księgi | 618190 | Wydatki na opłaty bankowe | Wydatek | Uznanie | Nie |  Po wybraniu **Księgi** w polu **Opłata** wybierz to konto w polu **Konto główne** na stronie płatności. |

Aby uzyskać więcej informacji, zobacz [Definiowanie opłat od płatności odbiorcy](../accounts-receivable/tasks/establish-customer-payment-fees.md).

## <a name="posting-accounts-for-charges-codes"></a>Księgowanie kont dla kodów opłat

Jeśli oprócz towarów w wierszu mają być śledzone kwoty sprzedaży, można używać kodów opłat. Na przykład, możesz pobierać opłaty za transport i przeładunek od swoich klientów lub możesz ponosić pewne opłaty za transport i przeładunek wewnętrznie. W tym przypadku można określić, czy kwoty są księgowane na kontach wydatków czy dodawane do kosztu towarów.

Kody opłat można tworzyć dla rozrachunków z odbiorcami i rozrachunków z dostawcami. Podczas konfigurowania kodu opłat należy zdefiniować księgowanie. Księgowanie steruje kontem debetowym i kontem kredytowym. Dla każdego kodu obciążeń, który tworzysz, możesz wybrać typ księgowania, który będzie używany. Poniższa tabela pokazuje typowe przykłady kodów opłat dla należności.

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Opis |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Opłata | 411400 | Dochody – Opłaty | Przychód | Środki | Nie | **Przykład dla niewystarczających środków:** Obciążenie konta klienta/ sprzedawcy i uznanie konta księgi |
| Zamówienie, fracht | 403500 | Przychód – transport | Przychód | Środki | Nie | **Przykład dla frachtu, którym obciążany jest klient:** Obciążenie konta klienta/sprzedawcy i uznanie konta księgi głównej |
| Rabat\* | 403200 | Rabat | Przychód | Uznanie | Nie | **Przykład rabatu dla klienta:** Obciążenie konta księgowego i uznanie konta klienta/ sprzedawcy |

\* W przypadku przykładu rabatu księgowanie jest używane tylko po dodaniu kodu opłat do nagłówka lub wiersza zamówienia zakupu. Zaawansowane funkcje rabatów dostępne w Microsoft Dynamics 365 Supply Chain Management zapewnia większą kontrolę i automatyzację rabatów. Aby uzyskać więcej informacji, zobacz temat [Rabaty dla klientów – informacje](../../supply-chain/sales-marketing/tasks/process-customer-rebates.md).

W poprzedniej tabeli pokazano trzy typowe przykłady typów księgowania, których można użyć dla kodów opłat. Należy go używać jako wskazówki i próbek. Nie dostarcza on pełnej listy wszystkich możliwych kombinacji lub typów księgowania, które mogą być używane.

Aby uzyskać więcej informacji, zobacz [Tworzenie kodów opłat](../accounts-receivable/create-charges-codes.md).

## <a name="posting-accounts-for-commissions"></a>Konta księgowania prowizji

Możesz opcjonalnie skonfigurować system tak, aby obliczał prowizje dla przedstawiciela handlowego lub grupy przedstawicieli handlowych na danym zamówieniu sprzedaży. Jeśli włączysz tę funkcjonalność, musisz skonfigurować konto księgowania, które będzie używane do obliczania prowizji. Konfiguracji tej dokonuje się na stronie **Księgowanie prowizji** w module **Sprzedaż i marketing**.

Aby uzyskać więcej informacji, zobacz [Ustalanie zasad prowizji od sprzedaży](../../supply-chain/sales-marketing/tasks/set-up-sales-commission-rules.md).
