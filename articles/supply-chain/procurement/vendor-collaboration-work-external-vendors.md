---
title: Współpraca z dostawcami zewnętrznymi przy użyciu modułu Współpraca z dostawcami
description: W tym temacie wyjaśniono, jak pracownicy działu zakupów mogą współpracować z zewnętrznymi dostawcami w celu wymiany informacji o zamówieniach zakupu i zapasach konsygnacyjnych.
author: mkirknel
manager: tfehr
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, VendVendorPortalInvoicePart, PurchaseOrderResponseActionRemarks, PurchVendorPortalAllResponse, PurchOrderInExternalReview, PurchVendorPortalPendingResponsesPart, PurchVendorPortalResponses, PurchVendorPortalConfirmedOpenOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 82249f460e5ddce9b9d43906008a3248a80daafb
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435625"
---
# <a name="vendor-collaboration-with-external-vendors"></a>Współpraca z dostawcami zewnętrznymi przy użyciu modułu Współpraca z dostawcami

[!include [banner](../includes/banner.md)]

Moduł **Współpraca z dostawcami** jest przeznaczony dla dostawców, którzy nie ma mają systemów elektronicznej wymiany danych (EDI) zintegrowanych z Microsoft Dynamics 365 Supply Chain Management. Umożliwia dostawcom pracę z zamówieniami zakupu (PO), fakturami, zapasami konsygnacyjnymi i zapytaniami ofertowymi (RFQ), a także uzyskanie dostępu do części danych głównych dostawcy. W tym temacie wyjaśniono możliwości współpracy z zewnętrznymi dostawcami, którzy używają interfejsu współpracy z dostawcami do wykonywania operacji na zamówieniach zakupu, zapytaniach ofertowych i zapasach konsygnacyjnych. Wyjaśniono także sposoby konfigurowania określonych dostawców do używania portalu współpracy z dostawcami oraz sposoby definiowania informacji wyświetlanych wszystkim dostawcom podczas odpowiadania na zamówienie zakupu.

Aby uzyskać więcej informacji o tym, co zewnętrzni dostawcy mogą robić w interfejsie współpracy z dostawcami, zobacz [Współpraca dostawców z odbiorcami](vendor-collaboration-work-customers-dynamics-365-operations.md).

> [!NOTE]
> Informacje na temat współpracy z dostawcą w tym temacie dotyczą tylko aktualnej wersji rozwiązania Supply Chain Management. W systemie Microsoft Dynamics AX 7.0 (luty 2016 r.) i aplikacji Microsoft Dynamics AX w wersji 7.0.1 (maj 2016 r.) do współpracy z dostawcami służy moduł **Portal dostawców**. Informacje o module **Portal dostawców** zawiera temat [Współpraca z dostawcami za pomocą portalu dostawców](collaborate-vendors-vendor-portal.md).

Aby uzyskać więcej informacji o tym, jak dostawcy mogą wykorzystywać portal współpracy z dostawcami w procesach fakturowania, zobacz [Obszar roboczy fakturowania w portalu współpracy z dostawcami](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md). Aby uzyskać więcej informacji o inicjowaniu obsługi nowych użytkowników portalu współpracy z dostawcami, zobacz [Zarządzanie użytkownikami portalu współpracy z dostawcami](manage-vendor-collaboration-users.md).

## <a name="defining-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>Definiowanie informacji wyświetlanych dostawcom podczas odpowiadania na zamówienia zakupu

Kiedy dostawcy odpowiadają na wysłane im zamówienie zakupu, widzą jedno z trzech pól komunikatu, w którym muszą potwierdzić zamiar zaakceptowania zamówienia zakupu, odrzucenia go lub zaakceptowania ze zmianami. Informacje niezbędne do pokazania dostawcy w tym momencie mogą być specyficzne dla firmy, dlatego można określić tekst, który będzie wyświetlany w każdym komunikacie potwierdzenia. Na przykład tekst może informować dostawcę o następnych krokach w procesie lub o warunkach i postanowieniach.

Aby określić tekst, który jest pokazywany w odpowiedzi na zamówienie zakupu, wykonaj opisane poniżej czynności:

1. Na stronie **Informacje dla dostawców odpowiadających na zamówienia zakupu** wybierz typ odpowiedzi, a następnie opcję **Edytuj**.
2. W polu **Komunikat informacyjny** wprowadź informacje, które mają być widoczne w polu komunikatu dostawcy.

Jeśli zachodzi konieczność dodania komunikatów w więcej niż jednym języku, utwórz różne komunikaty i dla każdego określ odpowiedni kod języka. Komunikat dla każdego dostawcy będzie wyświetlany w języku, którego ten używa.

## <a name="setting-the-vendor-collaboration-options-for-a-specific-vendor"></a>Ustawianie opcji współpracy z dostawcami dla określonego dostawcy

Administrator konfiguruje ustawienia ogólne współpracy z dostawcą, takie jak role zabezpieczeń dostępne dla wszystkich dostawców, z którymi współpracujesz. Istnieją jednak ustawienia, które są różne dla różnych kont dostawców. Należy skonfigurować te ustawienia.

- Włączyć współpracę z dostawcami.
- Określ, czy dostawca ma widzieć informacje o cenie.

### <a name="enabling-vendor-collaboration"></a>Włączanie współpracy z dostawcami

Zanim będzie można tworzyć konta użytkowników u zewnętrznego dostawcy, należy skonfigurować konto dostawcy, aby umożliwić mu używanie portalu współpracy z dostawcami. Na stronie **Dostawcy** na karcie **Ogólne** ustaw pole **Aktywacja współpracy**. Dostępne są następujące opcje:

- **Aktywna (zamówienie zakupu zostało automatycznie potwierdzone)** — zamówienia zakupu są automatycznie potwierdzane, gdy dostawca akceptuje je bez zmian.
- **Aktywna (zamówienie zakupu nie zostało automatycznie potwierdzone)** — zamówienia zakupu muszą zostać ręcznie potwierdzone przez Twoją organizację po ich zaakceptowaniu przez dostawcę.

### <a name="specifying-whether-the-vendor-should-see-price-information"></a>Określanie czy dostawca ma widzieć informacje o cenie

Aby udostępnić informację o cenie zamówienia zakupu przez interfejs portalu współpracy z dostawcami, należy ustawić opcję **Ceny/kwota zamówienia zakupu** na karcie **Ustawienia domyślne zamówienia zakupu** dla konta dostawcy na **Tak**. Informacje o cenie obejmują cenę jednostkową, rabaty i opłaty.

## <a name="working-with-pos-when-vendor-collaboration-is-used"></a>Praca z zamówieniami zakupu podczas używania portalu współpracy z dostawcami

### <a name="sending-a-po-to-a-vendor"></a>Wysyłanie zamówienia zakupu do dostawcy

Punkt sprzedaży jest przygotowany w Supply Chain Management Gdy zamówienie zakupu ma stan **Zatwierdzone**, można je wysłać do dostawcy, wybierając opcję **Wyślij w celu potwierdzenia** dostępną na stronie **Zamówienie zakupu**. Stan zamówienia zakupu zmieni się na **W trakcie analizy zewnętrznej**. Po wysłaniu zamówienia zakupu dostawca widzi je na stronie **Zamówienia zakupu do przeglądu** w interfejsie współpracy z dostawcami. Dostawca może zaakceptować zamówienie zakupu, odrzucić lub zasugerować jego modyfikację. Dostawca może również dodać komentarze w celu przekazania informacji, np. o zmianach w zamówieniu zakupu. Jeśli chcesz zwrócić uwagę dostawcy na nowe zamówienie zakupu, możesz je wysłać w wiadomości e-mail z systemu zarządzania drukowaniem.

### <a name="confirmation-and-acceptance-of-a-po-by-a-vendor"></a>Potwierdzanie i akceptacja zamówienia zakupu przez dostawcę

Po zaakceptowaniu zamówienia zakupu przez dostawcę może ono zostać automatycznie potwierdzone lub konieczne może być potwierdzenie go ręcznie. Zachowanie zależy od tego, czy dla dostawcy w polu **Aktywacja współpracy** ustawiono opcję **Aktywna (zamówienie zakupu zostało automatycznie potwierdzone)** czy **Aktywna (zamówienie zakupu nie zostało automatycznie potwierdzone)**.

W poniższej tabeli przedstawiono typową wymianę informacji, w zależności od odpowiedzi dostawcy na wysłanie mu zamówienia zakupu do potwierdzenia.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr>
<th>Odpowiedź dostawcy</th>
<th>Wynik</th>
</tr>
</thead>
<tbody>
<tr class="even">
<td>Dostawca <strong>akceptuje</strong> zamówienie, a rozwiązanie Supply Chain Management jest skonfigurowane w celu automatycznego potwierdzania zamówienia zakupu zaakceptowanego przez dostawcę.</td>
<td>Stan zamówienia jest zaktualizowany do <strong>Potwierdzone</strong>. Jeśli z jakiegoś powodu nie można zaktualizować zamówienia, odpowiedź dostawcy i tak zostanie zarejestrowana jako <strong>Zaakceptowane</strong>, ale zamówienie zakupu będzie nadal miało stan <strong>W trakcie analizy zewnętrznej</strong>. 

Zamówienie zakupu wysłane do dostawcy i mające stan <strong>W trakcie analizy zewnętrznej</strong> jest aktualizowane o potwierdzone daty dostawy w wierszach. Ta aktualizacja inicjuje nową wersję, która automatycznie zostanie ustawiona na stan <strong>Potwierdzone</strong>. Po potwierdzeniu zamówienia zakupu pojawi się ono w interfejsie współpracy z dostawcami.</td>
</tr>
<tr class="odd">
<td>Dostawca <strong>akceptuje</strong> zamówienie, a rozwiązanie Supply Chain Management nie&#39;jest skonfigurowane w celu automatycznego potwierdzania zamówienia zakupu zaakceptowanego przez dostawcę.</td>
<td>Odpowiedź dostawcy zostanie zarejestrowana jako <strong>Zaakceptowane</strong>, ale zamówienie zakupu będzie nadal miało stan <strong>W trakcie analizy zewnętrznej</strong>.

Zamówienie zakupu wysłane do dostawcy i mające stan <strong>W trakcie analizy zewnętrznej</strong> jest aktualizowane o potwierdzone daty dostawy w wierszach. Ta aktualizacja inicjuje nową wersję, która automatycznie zostanie ustawiona na stan <strong>W trakcie analizy zewnętrznej</strong>. Następnie można ręcznie potwierdzić zamówienie zakupu.</td>
</tr>
<tr class="even">
<td>Dostawca <strong>odrzuca</strong> zamówienie.</td>
<td>Odpowiedź dostawcy zostanie zarejestrowana jako <strong>Odrzucone</strong>, a zamówienie zakupu będzie nadal miało stan <strong>W trakcie analizy zewnętrznej</strong>. Odrzucenie jest odbierane razem z notatkami dostawcy.</td>
</tr>
<tr class="odd">
<td>Dostawca <strong>akceptuje</strong> zamówienie <strong>ze zmianami</strong>. Zmiany są sugerowane na poziomie wierszy. Dostawca może zaakceptować lub odrzucić pojedyncze wiersze. Poniżej przedstawiono niektóre inne zmiany, które może sugerować dostawca:
<ul>
<li>Zmiana dat lub ilości.</li>
<li>Podział wierszy dla różnych dat dostawy lub ilości.</li>
<li>Zastąpienie towaru.</li>
</ul>
Dostawca nie może zmienić informacji o cenach ani opłat. Dostawca może jednak sugerować te zmiany za pomocą uwag.</td>
<td>Odpowiedź dostawcy zostanie zarejestrowana jako <strong>Zaakceptowano ze zmianami</strong>, a zamówienie zakupu będzie nadal miało stan <strong>W trakcie analizy zewnętrznej</strong>. Stany pokazują typy zmian zasugerowanych przez dostawcę. Aby uzyskać informacje na temat automatycznego wprowadzania zmian, patrz sekcja &quot;Aktualizowanie zamówienia zakupu o zmiany sugerowane przez dostawcę&quot; w dalszej części tego tematu. </td>
</tr>
</tbody>
</table>

Można użyć obszaru roboczego **Przygotowanie zamówienia zakupu** do monitorowania, na które zamówienia zakupu dostawca odpowiedział. Ten obszar roboczy zawiera dwie listy z zamówieniami zakupu o stanie **W trakcie analizy zewnętrznej**:

- W trakcie przeglądu zewnętrznego (wymaga wykonania akcji)
- W trakcie analizy zewnętrznej, oczekuje na odpowiedź dostawcy

### <a name="changing-a-po"></a>Zmiana zamówienia zakupu

Aby zmodyfikować zamówienie zakupu, na które dostawca już odpowiedział, należy wysłać nowe zamówienie zakupu do dostawcy. Nowe zamówienie będzie miało sufiks wersji wskazujący, że jest to zmodyfikowana wersja zamówienia zakupu, które zostało wcześniej wysłane. Na stronie **Historia potwierdzeń zamówień zakupu przez dostawcę** Ty i Twoi dostawcy możecie śledzić historię każdego zamówienia. Poprzednio potwierdzona wersja zamówienia zakupu pozostaje na liście potwierdzonych zamówień zakupu do czasu potwierdzenia nowego zamówienia zakupu.

### <a name="canceling-a-po"></a>Anulowanie zamówienia zakupu

Po anulowaniu zamówienia zakupu jego stan zmienia się na **Zatwierdzone**. Następnie zamówienie zakupu trzeba jeszcze raz wysłać do dostawcy, aby potwierdził lub odrzucił anulowanie. Po potwierdzeniu anulowania zamówienie zakupu pojawi się na liście potwierdzonych zamówień zakupu dostawcy jako **Anulowane**.

### <a name="adding-attachments-to-a-po"></a>Dodawanie załączników do zamówienia zakupu

Za pomocą systemu zarządzania dokumentami można do zamówienia zakupu dodawać załączniki, takie jak pliki, obrazy i notatki. Załączniki typu **Zewnętrzne** będą widoczne dla dostawcy po wysłaniu mu zamówienia zakupu.

## <a name="updating-a-po-when-a-vendor-suggests-changes"></a>Aktualizowanie zamówienia zakupu o zmiany sugerowane przez dostawcę

Jeżeli dostawca odpowie na zamówienie zakupu i zaproponuje zmiany, następnym krokiem jest zareagowanie na odpowiedź.

W obszarze roboczym **Przygotowanie zamówienia zakupu** na liście **W trakcie przeglądu zewnętrznego** (wymaga wykonania akcji) możesz zidentyfikować zamówienie zakupu, które dostawca zaakceptował ze zmianami. Z tej listy można także przejść do odpowiedzi dostawcy,

W odpowiedzi dostawca może zmienić następujące informacje w nagłówku:
 
- Odwołanie do dokumentu dostawcy
- Metoda dostawy
- Warunki dostawy
- Potwierdzona data dostawy

Dostawca można również dodać notatkę lub załącznik.

W wierszach dostawca może zmienić ilość i daty dostawy, dodać notatki i załączniki, odrzucić wiersz, zastąpić wiersz innym produktem wprowadzonym tekstowo oraz podzielić wiersz na wiele dostaw. Stan wiersza różni się w zależności od zmian które zasugerował dostawca:
    
- **Zaakceptowano ze zmianami**
- **Odrzucone**
- **Zastąpiono** — w tym przypadku dodawany jest kolejny wiersz ze stanem **Substytut**.
- **Potwierdzone**
- **Podziel do harmonogramu** — w tym przypadku dodawane są kolejne wiersze ze stanem **Wiersze harmonogramu**.

Jeśli wiersz nie ma żadnych zmian, otrzymuje stan **Zaakceptowane**.

W odpowiedzi stany wierszy wskazują typy zmian wprowadzonych przez dostawcę. Ponadto wszystkie zmodyfikowane pola są wyświetlane pogrubioną czcionką, aby ułatwić identyfikowanie zmian.

Zamówienie zakupu można zaktualizować, wybierając opcję **Przetwórz aktualizację zamówienia zakupu** w odpowiedzi albo pojedynczo w wierszach. Pole **Czy aktualizacja zamówienia zakupu została przetworzona?** w nagłówku i wierszach określają, czy system przetworzył nagłówek lub wiersze w celu zaktualizowania zamówienia zakupu o wszelkie potencjalne zmiany wynikające z odpowiedzi. Akcję **Przetwórz aktualizację zamówienia zakupu** można uruchomić tylko raz dla każdego nagłówka lub wiersza.

Nie wszystkimi sugerowanymi zmianami można zaktualizować zamówienie zakupu. Tylko aktualizacje nagłówka oraz aktualizacje dat i ilości w wierszach mogą być automatycznie wprowadzanie w zamówieniu zakupu. W przypadku innych zmian należy ręcznie zaktualizować zamówienie zakupu. W takim przypadku wartość pola **Czy aktualizacja zamówienia zakupu została przetworzona?** to **Aktualizacja ręczna**. Jeżeli na przykład dostawca sugeruje, że wiersz powinie zostać podzielony do harmonogramu, tę zmianę należy wprowadzić ręcznie.

Każdy wiersz, który ma stan **Zaakceptowane** będzie miał potwierdzoną datę dostawy. Po uruchomieniu akcji **Przetwórz aktualizację zamówienia zakupu** ta data jest aktualizowana w zamówieniu zakupu. Uwagi i załączniki nie są automatycznie przenoszone do bieżącego zamówienia zakupu. Ponadto w przypadku aktualizacji bieżącego zamówienia zakupu za pomocą akcji **Przetwórz aktualizację zamówienia zakupu** umowy handlowe nie będą ponownie weryfikowane w wierszach zamówienia zakupu.

## <a name="po-statuses-and-versions"></a>Stany i wersje zamówień zakupu

W tej sekcji opisano różne stany, które może przyjmować zamówienie zakupu, aż do etapu potwierdzenia. Opisano również, kiedy nowe wersje zamówienia zakupu będą dostępne dla dostawcy. Zachowanie to się różni w zależności od tego, czy do zamówień sprzedaży jest stosowany proces zarządzania zmianami. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Wersji i stany, jeśli nie jest używane zarządzanie zmianami

W poniższej tabeli pokazano przykład zmian stanu i wersji, przez jakie może przechodzić zamówienie zakupu.

| Akcja | Stan i wersja |
|--------|--------------------|
| Pierwotna wersja zamówienia zakupu jest tworzona w programie Supply Chain Management. | Ma ona stan **Zatwierdzone**. |
| Zamówienie zakupu jest wysyłane do dostawcy. | Wersja jest rejestrowana w interfejsie współpracy z dostawcami, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**. |
| Dostawca wysyła odpowiedź **Zaakceptowano ze zmianami**. | Stan to nadal **W trakcie analizy zewnętrznej**. |
| Wprowadzasz kilka zmian, o które prosił dostawca. | Stan zostaje zmieniony na **Zatwierdzone**. |
| Wysyłasz nową wersję zamówienia zakupu do dostawcy. | Nowa wersja jest rejestrowana w interfejsie współpracy z dostawcami, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**. |
| Dostawca akceptuje nową wersję zamówienia zakupu. | Stanem jest nadal **W trakcie analizy zewnętrznej**, chyba że dostawca jest skonfigurowany do automatycznego ustawiania zamówień zakupu ma stan **Potwierdzone** w momencie akceptacji. |

Dostawcy nie muszą potwierdzać zamówień zakupu w interfejsie współpracy z dostawcami. Zamiast tego mogą również wysłać wiadomość e-mail lub zawiadomić o przyjęciu zamówienia zakupu przez inne kanały komunikacji. Następnie można ręcznie potwierdzić zamówienie. W takim przypadku zobaczysz ostrzeżenie informujące, że trwa potwierdzanie zamówienia, nawet jeśli nie ma odpowiedzi od dostawcy. Zamówienie zakupu pojawi się wtedy w historii potwierdzeń jako otwarte zamówienie potwierdzone, które nie ma żadnych odpowiedzi. W tym momencie dostawca nie będzie już mógł potwierdzić ani odrzucić zamówienia zakupu.

> [!NOTE]
> Wersją zamówienia zakupu dostępną dla innych procesów w rozwiązaniu Supply Chain Management jest zawsze najnowsza wersja, nawet jeśli jeszcze nie została zarejestrowana w interfejsie współpracy z dostawcami.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Wersji i stany, jeśli jest używane zarządzanie zmianami

Jeśli dla zamówień zakupu włączono funkcję zarządzania zmianami, zamówienia zakupu przejdą przez przepływ pracy zatwierdzania aż do osiągnięcia stanu **Zatwierdzone**. Ten proces nie jest widoczny dla dostawcy.

W poniższej tabeli pokazano przykład zmian stanu i wersji, przez jakie może przechodzić zamówienie zakupu przy włączonej opcji zarządzania zmianami. Wersja jest rejestrowana po zatwierdzeniu zamówienia, a nie wtedy, gdy zamówienie zakupu zostanie wysłane do dostawcy lub potwierdzone.

| Akcja | Stan i wersja |
|--------|--------------------|
| Pierwotna wersja zamówienia zakupu jest tworzona w programie Supply Chain Management. | Stan to **Wersja robocza**. |
| Zamówienie zakupu jest wysyłane do procesu zatwierdzania (Proces zatwierdzania jest procesem wewnętrznym, w którym dostawca nie uczestniczy). | Stan zmienia się z **Wersja robocza** na **W trakcie przeglądu** i dalej na **Zatwierdzenie**, jeśli zamówienie zakupu nie zostanie odrzucone w procesie zatwierdzania. Zatwierdzone zamówienie zakupu jest rejestrowane jako wersja. | 
| Zamówienie zakupu jest wysyłane do dostawcy. | Wersja jest rejestrowana w interfejsie współpracy z dostawcami, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**. |
| Wprowadzasz kilka zmian, o które prosił dostawca, ręcznie lub za pomocą akcji **Przetwórz aktualizację zamówienia zakupu** w odpowiedzi na aktualizację zamówienia zakupu. | Stan zostaje zmieniony z powrotem na **Wersja robocza**. |
| Zamówienie zakupu jest wysyłane z powrotem do procesu zatwierdzania. | Stan zmienia się z **Wersja robocza** na **W trakcie przeglądu** i dalej na **Zatwierdzenie**, jeśli zamówienie zakupu nie zostanie odrzucone w procesie zatwierdzania. Alternatywnie można skonfigurować system w taki sposób, żeby modyfikacje w określonych polach nie wymagały ponownego zatwierdzania. W takim przypadku stan zmienia się najpierw na **Wersja robocza**, a następnie jest automatycznie aktualizowany do wartości **Zatwierdzone**. Zatwierdzone zamówienie zakupu jest rejestrowane jako nowa wersja. |
| Wysyłasz nową wersję zamówienia zakupu do dostawcy. | Nowa wersja jest rejestrowana w interfejsie współpracy z dostawcami, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**. |
| Dostawca zatwierdza nową wersję zamówienia zakupu. | Stan zmienia się na **Potwierdzone** automatycznie lub po otrzymaniu odpowiedzi od dostawcy i następnie ręcznym potwierdzeniu. |

## <a name="sharing-information-about-consignment-inventory"></a>Udostępnianie informacji o zapasach konsygnacyjnych

Jeśli używasz zapasów konsygnacyjnych, dostawcy mogą w interfejsie współpracy z dostawcami wyświetlać informacje na następujących stronach:

- **Zamówienia zakupu zużywające zapasy konsygnacyjne** — zamówienia zakupu dla zapasów konsygnacyjnych są generowane po zmianie właściciela zapasów z dostawcy na Twoją firmę. W tym samym momencie jest księgowany dokument przyjęcia produktów. Te zamówienia zakupu konsygnacyjnego są wyświetlane tylko na stronie **Zamówienia zakupu zużywające zapasy konsygnacyjne**. Nie są one umieszczane na stronie **Wszystkie potwierdzone zamówienia zakupu** w module **Portal współpracy z dostawcami**.
- **Produkty odebrane z zapasów konsygnacyjnych** — na tej stronie znajduje się lista wszystkich transakcji, w których własność produktów została przeniesiona z dostawcy na Twoją firmę. Dostawcy mogą używać tych informacji do fakturowania odbiorcy.
- **Dostępne zapasy konsygnacyjne** — na tej stronie są pokazane dostępne zapasy konsygnacyjne będące własnością dostawcy, które przyjęto do magazynu.

## <a name="working-with-rfqs-when-you-use-vendor-collaboration"></a>Praca z zapytaniami ofertowymi podczas używania portalu współpracy z dostawcami

W tej sekcji opisano interakcje między klientami a dostawcami podczas przetwarzania zapytań ofertowych. Wyjaśniono również, jak informacje są przekazywane do dostawców. Podstawowe omówienie obsługi przetwarzania zapytań ofertowych zawiera temat [Omówienie zapytań ofertowych (ZO)](request-quotations.md).

### <a name="alternates-attachments-amendments-and-returns"></a>Alternatywy, załączniki, zmiany i zwroty

- **Alternatywy** — w nagłówku sprawy ZO, można określić dopuścić alternatywy dla wierszy pozycji spoza katalogu. Po włączeniu alternatyw, dostawcy mogą dodawać wiersz alternatywny dla każdego żądanego wiersza.
- **Załączniki** — załączniki można dodawać zarówno na poziomie nagłówka, jak i na poziomie wiersza sprawy ZO. Załączniki można klasyfikować jako wewnętrzne lub zewnętrzne. Załączniki wewnętrzne można wyświetlić tylko po stronie klienta, natomiast dostawcy mogą wyświetlać załączniki zewnętrzne po ich wysłaniu.

    Dostawcy mogą również dodawać załączniki w ich odpowiedzi na ofertę. Te załączniki mogą być przeglądane po stronie klienta po wysłaniu przez dostawcę odpowiedzi na ofertę. Załączniki, dodawane przez dostawców są zawsze klasyfikowane jako zewnętrzne. Aby uzyskać dostęp do załącznika wysłanego przez dostawcę razem z ofertą, wybierz opcję **Załączniki ofert** lub **Załączniki wierszy ofert**.
    
    Aby otworzyć załączniki, które zostały wysłane razem z sprawą ZO, użyj w odpowiedzi symbolu spinacza do obsługi dokumentów.

- **Zmiany** — po ukończeniu zmiany istniejącej odpowiedzi ofert są usuwane, dzięki czemu mogą zostać zastąpione przez zaktualizowane wartości. Za pomocą arkuszy w sprawie ZO można przeglądać informacje, takie jak cena i ilość wiersza z poprzednich odpowiedzi na ofertę.

    Aby wymusić przetwarzanie zmiany, na stronie **Parametry modułu Zaopatrzenie i sourcing** na skróconej karcie **Zapytania ofertowe** ustaw opcję **Zablokuj ZO, gdy zostaną wysłane** na **Tak**. (Ta opcja jest ustawiona i wymagana dla sektora publicznego.)

- **Zwroty** — jeżeli dostawca przesłał ofertę, ale wymagane są dodatkowe lub zmodyfikowane informacje dotyczące sprawy ZO, klient może zwrócić ofertę do dostawcy. Dane z poprzednio przesłanej oferty są zachowywane, a dostawca wprowadzić wymagane modyfikacje bez konieczności ponownego uruchamiania procesu oferty.

## <a name="public-sector-extensions"></a>Rozszerzenia sektora publicznego

W przypadku sektora publicznego funkcje rozszerzone umożliwiają wysłanie sprawy ZO do dostawców i ich publikowanie. Po opublikowaniu ZO każdy, kto prosi o informacje może wyświetlić prace zgodne z większością przepisów dotyczących sektora publicznego. Wszystkie dostępne prace są widoczne na stronie listy **Otwarte opublikowane zapytania ofertowe**, a anulowane, oczekujące lub przyznane ZO można wyświetlić na stronie listy **Zamknięte opublikowane zapytania ofertowe**. Dokumenty te można także wyświetlić w witrynie poza rozwiązaniem Supply Chain Management dzięki integracji z następującymi jednostkami danych:

- Opublikowane zapytania ofertowe
- Wiersz opublikowanych zapytań ofertowych
- Załączniki nagłówka opublikowanych zapytań ofertowych

Te jednostki umożliwiają osobom, które nie są ustanowionym użytkownikami rozwiązania Supply Chain Management, ale mają anonimowy dostęp do witryny zewnętrznej, wyświetlenie dostępnych i zamkniętych prac. Ponadto rozszerzone funkcje akcji **Wysyłanie i publikowanie** umożliwiają użytkownikowi konfigurującemu proces ZO zdefiniowanie szablonu wiadomości e-mail. Następnie, gdy specjalista ds. zaopatrzenia tworzy sprawę ZO, musi wybrać szablon wiadomości e-mail w celu wysłania wymaganych informacji do dostawców w sprawie ZO. 

Użytkownik, który konfiguruje parametry procesu ZO może utworzyć wiele szablonów wiadomości e-mail. Te szablony wiadomości e-mail mogą zawierać zarówno tekst, jak i następujące tokeny wymiany. Tokeny zostaną zastąpione wartościami kontekstowych podczas tworzenia wiadomości e-mail.

- %RFQCase%
- %RFQCaseName%
- %bidType%
- %inviteOnly%
- %expiryDateTime%
- %requester%
- %requestingDepartment%
- %accountnum%
- %todaysdate%
- %createddate%

Jeśli zmiana jest wymagana i jest wysyłana po przesłaniu ZO , zapytanie ofertowe zostanie wysłane do wszystkich zaproszonych dostawców. Opublikowany dokument zostaną również zaktualizowane na stronie **Otwarte opublikowane zapytania ofertowe**.
