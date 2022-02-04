---
# required metadata
title: Menedżer ds. księgowości z dostawcami
description: 'W tym temacie wyjaśniono, w jaki sposób księgowanie jest skonfigurowane w rozrachunkach z dostawcami, i przedstawiono przykłady konfiguracji księgowania.'
author: rachel-profitt
ms.date: 01/19/2022
ms.topic: article
ms.prod: null
ms.technology: null
ms.search.form: 'VendPosting, VendPaymMode, VendCashDiscount, MarkupTable\_Vend, VendPaymFee'
audience: Application User
ms.reviewer: twheeloc
ms.custom: null
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: '2022-01-03'
ms.dyn365.ops.version: AX 7.0.0
---

# <a name="accounts-payable-posting"></a>Menedżer ds. księgowości z dostawcami

[!include [banner](../includes/banner.md)]

Głównym profilem księgowania w module **Rozrachunki z dostawcami** jest profil księgowania dostawcy. Ten profil księgowania określa konto podsumowujące używane podczas księgowania sald dostawcy w księdze głównej. Konto podsumowujące jest kontem głównym. Takie konto jest również nazywane kontem handlowym Rozrachunki z dostawcami.

Aby uzyskać więcej informacji, zobacz [Profile księgowania dostawców](../accounts-payable/vendor-posting-profiles.md).

W rozrachunkach z dostawcami jest dostępnych kilka konfiguracji księgowania oprócz profilu księgowania dostawcy. Poniższe sekcje zawierają więcej informacji o tych innych konfiguracjach księgowania.

## <a name="methods-of-payment-posting-accounts"></a>Konta księgowania metod płatności

Metody płatności określają sposób księgowania płatności w księdze głównej. Sterują one również zachowaniem danych wyjściowych płatności. Zazwyczaj dla każdego typu płatności stosowanego przez organizację tworzona jest jedna metoda płatności (na przykład gotówka, czek, karta kredytowa, zlecenie pieniężne i gotówka).

Pola w sekcji **Księgowanie** na skróconej karcie **Ogólne** na stronie **Metody płatności** (**Ustawienia > Rozrachunki z dostawcami > Metody płatności**) kontrolują sposób księgowania płatności w księdze głównej. Najpierw musisz wybrać wartość w **polu Typ konta**. Wybrane typ konta steruje działaniem pola **Konto płatności**. Zaleca się wybranie opcji **Bank** w polu **Typ konta**, a następnie wybranie konta bankowego w **polu Konto płatności**. Dzięki takiemu podejściu system będzie księgował płatność w poddarze Bank, które obsługuje uzgadnianie i inne procesy związane z gotówką. W poniższej tabeli pokazano przykład konfiguracji profilu księgowania, jeśli jest używasz modułu **Zarządzanie gotówką i bankami**.

| Typ księgowania | Typ konta | Przykład nazwy rachunku płatniczego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Opis |
|--------------|--------------|------------------------------|--------------|---------------|------------------|-------------|
| Bank | Bank | Bank of America | Konto bankowe połączone ze środekem trwałym | Uznanie | Nie | Dla każdej metody płatności wprowadź konto główne w **polu Konto płatności**. |

Jeśli nie planujesz korzystania z funkcji zarządzania gotówką i bankami, wybierz opcję **Księga** w polu **Typ konta**, a następnie wybierz konto główne w polu **Konto płatności**. W poniższej tabeli przedstawiono przykład konfiguracji profilu księgowania, jeśli **nie** korzystasz z Zarządzania gotówką i bankami.

| Typ księgowania | Typ konta |Przykład rachunku płatniczego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Opis |
|--------------|--------------|------------------------|--------------|---------------|------------------|-------------|
| Ledger | Ledger | 100100: Bank of America | Element zawartości | Uznanie | Nie | Dla każdej metody płatności wprowadź konto główne w **polu Konto płatności**. |

## <a name="bridging-accounts"></a>Konta pomostowe

Księgowanie pomostowe to dwuetapowy proces, który jest używany podczas księgowania płatności. Jest to funkcja opcjonalna, która może być używana na przykład z kontami bankowymi z zerowym saldem. Zapewnia to bezproblemowy i bardziej terminowy proces uzgadniania konta bankowego. W pierwszym kroku płatność jest księgowana na koncie tymczasowym (koncie pomostowym). W drugim kroku zaksięgowany wpis jest wycofywny i księgowany na koncie bankowym, gdy bank je wyczyści. W poniższej tabeli pokazano przykład konfiguracji profilu księgowania dla księgowania pomostowego.

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Opis |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Arkusz księgi | 130725 | Gotówka niezrachiwowana | Pasywa | Uznanie | Tak | Dla każdej metody płatności wprowadź konto główne w **polu Konto pomostowe**. |

Aby uzyskać więcej informacji, zobacz [temat Konfigurowanie i przetwarzanie płatności pomostowych](../accounts-receivable/set-up-and-process-bridged-payments.md).

## <a name="customer-cash-discounts-posting-accounts"></a>Konta księgowania rabatów gotówkowych odbiorcy

Jeśli organizacja otrzymuje rabaty gotówkowe od dostawców w zamian za szybką płatność, należy skonfigurować kody rabatów gotówkowych i określić sposób księgowania rabatów w księdze głównej. Dostępnych jest kilka opcji określania konta głównego używanego do księgowania rabatu gotówkowego odbiorcy.

Aby uzyskać więcej informacji, zobacz [Rabaty gotówkowe](../cash-bank-management/cash-discounts.md).

## <a name="payment-fee-posting-accounts"></a>Konta księgowania opłat od płatności

Opłaty umożliwiają automatyczne dodawanie opłaty do płatności dostawcy, jeśli obowiązuje zestaw warunków. Opłaty mogą zostać zapłacone dostawcy lub zaksięgowane na koncie bankowym jako wydatek. Oto kilka przykładów:

- Dostawca pobiera 3% łącznej płatności, jeśli płatność jest opłacana kartą kredytową.
- Opłaty bankowe są $1,00 za każdy przetwarzany przelew bankowy, a opłata jest naliczana wydatkowana.

Po skonfigurowaniu opłaty od płatności dla dostawcy, jeśli w polu **Opłata** zostanie ustawiona wartość **Dostawca**, pole **Konto główne** stanie się niedostępne, a do zaksięgowania opłaty system użyje profilu księgowania dostawcy. Jeśli w polu **Opłata** zostanie ustawiona wartość **Księga**, należy ustawić pole **Konto główne** na koncie głównym, na którym zostanie zaksięgowana opłata od płatności. Zazwyczaj to konto główne będzie kontem wydatków. W poniższej tabeli przedstawiono przykład konfiguracji profilu księgowania dla księgowania opłat.

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Opis |
|--------------|----------------------|---------------------------|--------------|----------------|------------------|-------------|
| Arkusz księgi | 618190 | Wydatki na opłaty bankowe | Wydatek | Uznanie | Nie | Po wybraniu **Księgi** w polu **Opłata** wybierz to konto w polu **Konto główne** na stronie **Opłata**. |

Aby uzyskać więcej informacji, zobacz [Definiowanie opłat od płatności dostawcy](../accounts-payable/tasks/define-vendor-payment-fees.md).

## <a name="charges-code-posting-accounts"></a>Konta księgowania kodów opłat

Jeśli oprócz towarów w wierszu ma być śledzone kwoty zakupów, można używać kodów opłat. Na przykład dostawca może na przykład naliczać od użytkownika opłaty frachtowe i manipulacyjnych albo poniesieć koszty transportu i opłaty manipulacyjnych wewnętrznie. W tym przypadku można określić, czy kwoty są księgowane na kontach wydatków czy dodawane do kosztu towarów.

Kody opłat można tworzyć dla rozrachunków z odbiorcami i rozrachunków z dostawcami. Podczas konfigurowania kodu opłat należy zdefiniować księgowanie. Księgowanie steruje kontem debetowym i kontem kredytowym. Podczas tworzenia kodów opłat można wybrać typ księgowania, który będzie używany dla każdego kodu opłat. W poniższej tabeli pokazano przykłady typowych kodów opłat dla rozrachunków z dostawcami na **stronie Kody opłat**.

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Opis |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Opłata od zakupu | Pozostaw pole puste. | Nie dotyczy | Towar | Uznanie | Nie | **Przykład opłaty za zakup towaru:** </p><ul><li>**Pole typu** debet = **Pozycja**</li><li>  **Pole typu** kredytu = **Odbiorca/Dostawca**.</li><li> W księgowanie towaru używane jest konto główne z profilu księgowania zapasów. |
| Zamówienie, fracht | 600120 | Transport do | Przychód | Uznanie | Nie | **Na przykład w przypadku frachtu płaconego dostawcy:** </p><ul><li>**Pole Typu** debetu = **Konto księgowe**</li><li> **Pole typu** kredytu = **Odbiorca/Dostawca** |
| Rabat\* | 503160 | Rabat dostawcy (przeciwko KWS)| Wydatek | Środki | Nie | **Przykład rabatu dostawcy:**</p><ul><li>**Pole typu** debetu = **Odbiorca/Dostawca**</li><li>**Pole Typu** kredytu = **Konto księgowe** |

\* W przypadku przykładu rabatu księgowanie jest używane tylko po dodaniu kodu opłat do nagłówka lub wiersza zamówienia zakupu. Zaawansowane funkcje rabatów dostępne w Microsoft Dynamics 365 Supply Chain Management zapewnia większą kontrolę i automatyzację rabatów. Aby uzyskać więcej informacji, zobacz [Rabaty dostawcy](../../supply-chain//procurement/vendor-rebates.md).

W poprzedniej tabeli pokazano trzy typowe przykłady typów księgowania, których można użyć dla kodów opłat. Należy go używać jako wskazówki i wyboru próbek. Nie dostarcza on pełnej listy wszystkich możliwych kombinacji lub typów księgowania, które mogą być używane.

Aby uzyskać więcej informacji, zobacz [Tworzenie kodów opłat](../accounts-receivable/create-charges-codes.md).
