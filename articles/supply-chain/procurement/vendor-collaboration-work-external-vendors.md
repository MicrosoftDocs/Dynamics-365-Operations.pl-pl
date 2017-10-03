---
title: "Współpraca z zewnętrznymi dostawcami"
description: "W tym temacie opisano, jak pracownicy działu zakupów mogą współpracować z zewnętrznymi dostawcami w celu wymiany informacji o zamówieniach zakupu i zapasach konsygnacyjnych."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: cbd099403f48b502ca74bcb38ae12decedb8f2da
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---

# <a name="vendor-collaboration-with-external-vendors"></a>Współpraca z zewnętrznymi dostawcami

[!include[banner](../includes/banner.md)]


W tym temacie opisano, jak pracownicy działu zakupów mogą współpracować z zewnętrznymi dostawcami w celu wymiany informacji o zamówieniach zakupu i zapasach konsygnacyjnych.

Moduł **Współpraca z dostawcami** jest przeznaczony dla dostawców, którzy nie ma mają systemów elektronicznej wymiany danych (EDI) zintegrowanych z programem Microsoft Dynamics 365 for Finance and Operations. Umożliwia on dostawcom pracę z zamówieniami zakupu, fakturami i zapasami konsygnacyjnymi. W tym temacie opisano możliwości współpracy z zewnętrznymi dostawcami, którzy używają interfejsu współpracy z dostawcami do wykonywania operacji na zamówieniach zakupu i zapasach konsygnacyjnych. Omówiono także sposoby konfigurowania określonych dostawców do używania portalu współpracy z dostawcami oraz sposoby definiowania informacji wyświetlanych wszystkim dostawcom podczas odpowiadania na zamówienie zakupu. Aby uzyskać więcej informacji o tym, co zewnętrzni dostawcy mogą robić w interfejsie współpracy z dostawcami, zobacz [Współpraca dostawców z odbiorcami](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Aby uzyskać więcej informacji o tym, jak dostawcy mogą wykorzystywać portal współpracy z dostawcami w procesach fakturowania, zobacz [Obszar roboczy fakturowania w portalu współpracy z dostawcami](/dynamics365/unified-operations/financials/accounts-payable/vendor-portal-invoicing-workspace). Aby uzyskać więcej informacji o inicjowaniu obsługi nowych użytkowników portalu współpracy z dostawcami, zobacz [Zarządzanie użytkownikami portalu współpracy z dostawcami](manage-vendor-collaboration-users.md).

Aby uzyskać więcej informacji o tym, jak dostawcy mogą wykorzystywać portal współpracy z dostawcami w procesach fakturowania, zobacz [Obszar roboczy fakturowania w portalu współpracy z dostawcami](/dynamics365/unified-operations/financials/accounts-payable/vendor-portal-invoicing-workspace). 

Aby uzyskać więcej informacji o inicjowaniu obsługi nowych użytkowników portalu współpracy z dostawcami, zobacz [Zarządzanie użytkownikami portalu współpracy z dostawcami](manage-vendor-collaboration-users.md).

## <a name="define-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>Definiowanie informacji wyświetlanych dostawcom podczas odpowiadania na zamówienia zakupu
Kiedy dostawcy odpowiadają na wysłane im zamówienie zakupu, widzą okno komunikatu, w którym muszą potwierdzić zamiar zaakceptowania zamówienia zakupu, odrzucenia go lub zaakceptowania ze zmianami. Informacje niezbędne do pokazania dostawcy w tym momencie mogą być specyficzne dla firmy, dlatego można określić tekst, który będzie wyświetlany w każdym z trzech komunikatów potwierdzenia. Na przykład tekst może informować dostawcę o następnych krokach w procesie lub o warunkach i postanowieniach.  

Aby określić tekst, który jest pokazywany w odpowiedzi na zamówienie zakupu:

1.  Otwórz stronę **Informacje dla dostawców odpowiadających na zamówienia zakupu**.
2.  Wybierz jeden z typów odpowiedzi.
3.  Kliknij przycisk **Edytuj**.
4.  W polu **Komunikat informacyjny** wprowadź informacje, które mają widzieć dostawcy.

Jeśli zachodzi konieczność dodania komunikatów w więcej niż jednym języku, utwórz różne komunikaty i dla każdego określ odpowiedni kod języka. Komunikat wyświetlany dostawcy będzie w języku, którego ten używa.

## <a name="set-the-vendor-collaboration-options-for-a-specific-vendor"></a>Ustawianie opcji współpracy z dostawcami dla określonego dostawcy
Ustawienia ogólne współpracy z dostawcami w programie Finance and Operations są konfigurowane przez administratora. Na przykład administrator określa, które role zabezpieczeń są dostępne dla wszystkich dostawców, z którymi współpracujesz. Istnieją też ustawienia, które są różne dla różnych dostawców, oraz trzeba ustawić następujące opcje:
-   Włączyć współpracę z dostawcami.
-   Zdecydować, czy dostawca ma widzieć informacje o cenach.

### <a name="enable-vendor-collaboration"></a>Włączanie współpracy z dostawcami

Zanim będzie można tworzyć konta użytkowników u zewnętrznego dostawcy, należy skonfigurować konto dostawcy, aby umożliwić mu używanie portalu współpracy z dostawcami. W tym celu na stronie **Dostawcy** na karcie **Ogólne** ustaw pole **Aktywacja współpracy** jako aktywne. Dostępne są dwie opcje do wyboru:

-   **Aktywna (zamówienie zakupu zostało automatycznie potwierdzone)** — zamówienia zakupu są automatycznie potwierdzane, gdy dostawca akceptuje je bez zmian.
-   **Aktywna (zamówienie zakupu nie zostało automatycznie potwierdzone)** — zamówienia zakupu muszą zostać ręcznie potwierdzone przez Twoją organizację po ich zaakceptowaniu przez dostawcę.

### <a name="decide-whether-you-want-the-vendor-to-see-price-information"></a>Decydowanie, czy dostawca ma widzieć informacje o cenach

Jeśli za pośrednictwem interfejsu współpracy chcesz udostępnić informacje o cenach, takie jak cena jednostkowa, rabaty i opłaty, należy w koncie dostawcy w **Ceny/kwota zamówienia zakupu** ustawić wartość **Tak**. Ta opcja jest dostępna na karcie **Ustawienia domyślne zamówienia zakupu**.

## <a name="work-with-pos-when-using-vendor-collaboration"></a>Praca z zamówieniami zakupu podczas używania portalu współpracy z dostawcami
### <a name="sending-a-po-to-the-vendor"></a>Wysyłanie zamówienia zakupu do dostawcy

Zamówienia zakupu są przygotowywane w programie Finance and Operations. Gdy zamówienie zakupu ma stan **Zatwierdzone**, można je wysłać do dostawcy za pomocą akcji **Wyślij w celu potwierdzenia** dostępnej na stronie **Zamówienie zakupu**. Stan zamówienia zakupu zmieni się na **W trakcie analizy zewnętrznej**. Po wysłaniu zamówienia zakupu dostawca widzi je na stronie **Zamówienia zakupu do przeglądu** w interfejsie współpracy z dostawcami. Dostawca może zaakceptować zamówienie, odrzucić lub zasugerować jego modyfikację. Dostawca może również dodać komentarze w celu przekazania informacji, np. o zmianach w zamówieniu zakupu. Jeśli chcesz zwrócić uwagę dostawcy na nowe zamówienie zakupu, możesz je wysłać e-mailem z systemu zarządzania drukowaniem.

### <a name="confirmation-and-acceptance-of-the-po-by-the-vendor"></a>Potwierdzanie i akceptacja zamówienia zakupu przez dostawcę

Gdy dostawca zaakceptuje zamówienie zakupu, może ono zostać potwierdzone automatycznie lub wymagać ręcznego potwierdzenia. Zależy to od tego, czy dla dostawcy w polu **Aktywacja dostawcy** ustawiono opcję **Aktywna (zamówienie zakupu zostało automatycznie potwierdzone)**, czy **Aktywna (zamówienie zakupu nie zostało automatycznie potwierdzone)**.  

W poniższej tabeli przedstawiono typową wymianę informacji, w zależności od odpowiedzi dostawcy na wysłanie mu zamówienia zakupu do potwierdzenia.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Odpowiedź dostawcy</strong></td>
<td><strong>Rezultat</strong></td>
</tr>
<tr class="even">
<td>Dostawca <strong>akceptuje</strong> zamówienie. W programie Finance and Operations skonfigurowano automatyczne potwierdzanie zamówień zakupu po ich zaakceptowaniu przez dostawców.</td>

<td>Stan zamówienia jest zaktualizowany do <strong>Potwierdzone</strong>. Jeśli z jakiegoś powodu nie można zaktualizować zamówienia, odpowiedź dostawcy i tak zostanie zarejestrowana jako <strong>Zaakceptowane</strong>, ale zamówienie zakupu będzie nadal miało stan <strong>W trakcie analizy zewnętrznej</strong>. 

Zamówienie zakupu wysłane do dostawcy i mające stan **W trakcie analizy zewnętrznej** jest aktualizowane o potwierdzone daty dostawy w wierszach. Aktualizacja inicjuje nową wersję, która automatycznie zostanie zaktualizowana do stanu **Potwierdzone**. Po potwierdzeniu zamówienia zakupu pojawi się ono w interfejsie współpracy z dostawcami.</td>
</tr>
<tr class="odd">
<td>Dostawca <strong>akceptuje</strong> zamówienie. W programie Finance and Operations nie skonfigurowano automatycznego potwierdzania zamówień zakupu po ich zaakceptowaniu przez dostawców.</td>
<td>Odpowiedź dostawcy zostanie zarejestrowana jako <strong>Zaakceptowane</strong>, ale zamówienie zakupu będzie nadal miało stan <strong>W trakcie analizy zewnętrznej</strong>.

Zamówienie zakupu wysłane do dostawcy i mające stan **W trakcie analizy zewnętrznej** jest aktualizowane o potwierdzone daty dostawy w wierszach. Aktualizacja inicjuje nową wersję, która otrzyma stan **W trakcie analizy zewnętrznej**. Wtedy będzie można ręcznie potwierdzić zamówienie zakupu.</td>

</tr>
<tr class="even">
<td>Dostawca <strong>odrzuca</strong> zamówienie.</td>
<td>Odpowiedź dostawcy zostanie zarejestrowana jako <strong>Odrzucone</strong>, a zamówienie zakupu będzie nadal miało stan <strong>W trakcie analizy zewnętrznej</strong>. Odrzucenie jest odbierane razem z notatkami dostawcy.</td>
</tr>
<tr class="odd">
<td>Dostawca <strong>akceptuje zamówienie ze zmianami</strong>. Zmiany są sugerowane na poziomie wierszy. Istnieje możliwość zaakceptowania lub odrzucenia poszczególnych wierszy. Inne możliwe zmiany:
<ul>
<li>Zmiana dat lub ilości.</li>
<li>Podział wierszy dla różnych dat dostawy lub ilości.</li>
<li>Zastąpienie towaru.</li>
</ul>
Informacje o cenach i opłatach nie mogą być zmieniane przez dostawcę. Sugestie dotyczące zmian mogą być dokonywane za pomocą notatek.</td>
<td>Odpowiedź dostawcy zostanie zarejestrowana jako <strong>Zaakceptowano ze zmianami</strong>, a zamówienie zakupu będzie nadal miało stan <strong>W trakcie analizy zewnętrznej</strong>. Stany pokazują, jakie typy zmian zasugerował dostawca. Aby uzyskać informacje na temat automatycznego wprowadzania zmian, przeczytaj sekcję poniżej dotyczącą aktualizowania zamówienia zakupu, gdy dostawca proponuje zmiany. </td>
</tr>
</tbody>
</table>

Można użyć obszaru roboczego **Przygotowanie** **zamówienia zakupu** do monitorowanie, na które zamówienia zakupu dostawca odpowiedział. Ten obszar roboczy zawiera dwie listy z zamówieniami zakupu o stanie **W trakcie analizy zewnętrznej**:

-   W trakcie przeglądu zewnętrznego (wymaga wykonania akcji).
-   W trakcie analizy zewnętrznej, oczekuje na odpowiedź dostawcy.

### <a name="changing-a-po"></a>Zmiana zamówienia zakupu

Aby zmodyfikować zamówienie zakupu, na które już odpowiedziano, należy wysłać nowe zamówienie zakupu do dostawcy. Nowe zamówienie będzie miało sufiks wersji wskazujący, że jest to zmodyfikowana wersja zamówienia zakupu, które zostało wcześniej przekazane. Na stronie **Historia potwierdzeń zamówień zakupu przez dostawcę** Ty i Twoi dostawcy możecie śledzić historię każdego zamówienia. Poprzednio potwierdzona wersja zamówienia zakupu pozostaje na liście potwierdzonych zamówień zakupu do czasu potwierdzenia nowego zamówienia zakupu.

### <a name="cancelling-a-po"></a>Anulowanie zamówienia zakupu

Po anulowaniu zamówienia zakupu jego stan zmienia się na **Zatwierdzone**. Zamówienie zakupu trzeba odesłać dostawcy za pośrednictwem portalu, tak aby dostawca mógł potwierdzić lub odrzucić anulowanie. Po potwierdzeniu anulowania zamówienie zakupu pojawi się na liście potwierdzonych zamówień zakupu dostawcy jako **Anulowane**.

### <a name="adding-attachments-to-a-po"></a>Dodawanie załączników do zamówienia zakupu

Za pomocą systemu zarządzania dokumentami można do zamówienia zakupu dodawać załączniki, takie jak pliki, obrazy i notatki. Załączniki typu **Zewnętrzne** będą widoczne dla dostawcy po wysłaniu mu zamówienia zakupu.

## <a name="update-the-po-when-a-vendor-suggests-changes"></a>Aktualizowanie zamówienia zakupu o zmiany sugerowane przez dostawcę
Gdy dostawca odpowie na zamówienie zakupu i zaproponuje zmiany, następnym krokiem jest zareagowanie na odpowiedź.
W obszarze roboczym **Przygotowanie zamówienia zakupu** na liście W trakcie przeglądu zewnętrznego (wymaga wykonania akcji) możesz zidentyfikować zamówienie, na które dostawca odpowiedział, ponieważ jest oznaczone jako zaakceptowane ze zmianami. Na liście W trakcie przeglądu zewnętrznego (wymaga wykonania akcji) można również przejść do odpowiedzi dostawcy. W odpowiedzi dostawca może zmienić następujące informacje w nagłówku.
 
-   Odwołanie do dokumentu dostawcy
-   Metoda dostawy
-   Warunki dostawy
-   Potwierdzona data dostawy

Dostawca można również dodać notatkę lub załącznik.

W wierszach dostawca może zmienić ilość i daty dostawy, dodać notatki i załączniki, odrzucić wiersz, zastąpić wiersz innym produktem wpisanym tekstowo oraz podzielić wiersz na wiele dostaw. W zależności od tego, jakie zmiany zaproponuje dostawca, stan wiersza będzie miał różne wartości:
    
-   **Zaakceptowano ze zmianami**
-   **Odrzucone**
-   **Zastąpiono** W tym przypadku zostanie dodany kolejny wiersz ze stanem **Substytut**.
-   **Potwierdzone** Podziel do harmonogramu W tym przypadku zostaną dodane kolejne wiersze ze stanem **Wiersze harmonogramu**.

Jeśli wiersz nie ma żadnych zmian, otrzymuje stan **Zaakceptowane**.

W odpowiedzi widać opisane wyżej stany wierszy, które wskazują typy zmian wprowadzonych przez dostawcę. Ponadto wszystkie zmodyfikowane pola są wyświetlane pogrubioną czcionką, aby ułatwić identyfikowanie zmian.

Zamówienie zakupu można zaktualizować, klikając opcję **Przetwórz aktualizację zamówienia zakupu** w odpowiedzi albo pojedynczo w wierszach. Wskaźnik **Czy aktualizacja zamówienia zakupu została przetworzona?** w nagłówku i wierszach pozwala zobaczyć, czy system przetworzył nagłówek lub wiersze w celu zaktualizowania zamówienia zakupu o wszelkie potencjalne zmiany wynikające z odpowiedzi. Proces **Przetwórz aktualizację zamówienia zakupu** można uruchomić tylko raz dla każdego nagłówka lub wiersza.

Nie wszystkimi sugerowanymi zmianami można zaktualizować zamówienie zakupu. Tylko aktualizacje nagłówka oraz aktualizacje dat i ilości w wierszach mogą być automatycznie wprowadzanie w zamówieniu zakupu. W przypadku innych zmian należy ręcznie zaktualizować zamówienie zakupu. W takim przypadku wskaźnik **Czy aktualizacja zamówienia zakupu została przetworzona?** pokazuje wartość **Aktualizacja ręczna**. Przykładem zmiany, którą należy wprowadzić ręcznie, byłaby sugestia dostawcy, aby podzielić wiersz na harmonogram.

Wiersz o stanie **Zaakceptowane** ma potwierdzoną datę dostawy, która zaktualizuje zamówienie zakupu podczas wykonywania operacji **Przetwórz aktualizację zamówienia zakupu**. Uwagi i załączniki nie będą automatycznie przenoszone do bieżącego zamówienia zakupu. Należy zauważyć, że w przypadku aktualizacji bieżącego zamówienia zakupu za pomocą operacji **Przetwórz aktualizację zamówienia zakupu** umowy handlowe nie będą ponownie weryfikowane w wierszach zamówienia zakupu.


## <a name="po-statuses-and-versions"></a>Stany i wersje zamówień zakupu
W tej sekcji opisano różne stany, które może przyjmować zamówienie zakupu, aż do etapu potwierdzenia. Wyjaśniono również, w których momentach nowe wersje zamówienia zakupu będą dostępne dla dostawcy. Zachowanie to się różni w zależności od tego, czy do zamówień sprzedaży jest stosowany proces zarządzania zmianami. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Wersji i stany, jeśli nie jest używane zarządzanie zmianami

W poniższej tabeli pokazano przykład zmian stanu i wersji, przez jakie może przechodzić zamówienie zakupu.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Akcja**                                                               | **Stan i wersja**                                                                                                                                       |
| Pierwotna wersja zamówienia zakupu jest tworzona w programie Finance and Operations. | Ma ona stan **Zatwierdzone**.                                                                                                                                  |
| Zamówienie zakupu jest wysyłane do dostawcy.                                            | Wersja jest rejestrowana w interfejsie współpracy z dostawcami, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**.                                          |
| Dostawca wysyła odpowiedź **Zaakceptowano ze zmianami**.                  | Stan to nadal **W trakcie analizy zewnętrznej**.                                                                                                                  |
| Wprowadzasz kilka zmian, o które prosił dostawca.                  | Stan zostaje zmieniony na **Zatwierdzone**.                                                                                                                        |
| Wysyłasz nową wersję zamówienia zakupu do dostawcy.                        | Nowa wersja jest rejestrowana w interfejsie współpracy z dostawcami, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**.                                      |
| Dostawca akceptuje nową wersję zamówienia zakupu.                            | Stanem jest nadal **W trakcie analizy zewnętrznej**, chyba że dostawca jest skonfigurowany do automatycznego ustawiania zamówienia zakupu do stanu **Potwierdzone** w momencie akceptacji. |


Dostawcy nie muszą potwierdzać zamówień zakupu w interfejsie współpracy z dostawcami. Zamiast tego mogą również wysłać wiadomość e-mail lub zawiadomić o przyjęciu zamówienia zakupu przez inne kanały komunikacji. Wtedy można potwierdzić zamówienie ręcznie w programie Finance and Operations. W takim przypadku zobaczysz ostrzeżenie informujące, że trwa potwierdzanie zamówienia, nawet jeśli nie ma odpowiedzi od dostawcy. Zamówienie zakupu pojawi się wtedy w historii potwierdzeń jako otwarte zamówienie potwierdzone, które nie ma żadnych odpowiedzi. Dostawca nie będzie już mógł potwierdzić ani odrzucić zamówienia zakupu.  


>[!NOTE]
>Wersją zamówienia zakupu dostępną dla innych procesów w programie Dynamics 365 for Finance and Operations jest zawsze najnowsza wersja, nawet jeśli jeszcze nie została zarejestrowana w interfejsie współpracy z dostawcami.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Wersji i stany, jeśli jest używane zarządzanie zmianami

Jeśli dla zamówień zakupu włączono funkcję zarządzania zmianami, zamówienie przejdzie przez przepływ pracy zatwierdzania aż do osiągnięcia stanu **Zatwierdzone**. Ten proces nie jest widoczny dla dostawcy.  

W poniższej tabeli pokazano przykład zmian stanu i wersji, przez jakie może przechodzić zamówienie zakupu przy włączonej opcji zarządzania zmianami. Wersja jest rejestrowana po zatwierdzeniu zamówienia, a nie wtedy, gdy zamówienie zakupu zostanie wysłane do dostawcy lub potwierdzone.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Akcja**                                                               | **Stan i wersja**                                                                                                                                       |
| Pierwotna wersja zamówienia zakupu jest tworzona w programie Finance and Operations.      | Stan to **Wersja robocza**.  |
| Zamówienie zakupu jest wysyłane do procesu zatwierdzania (Proces zatwierdzania jest procesem wewnętrznym, w którym dostawca nie uczestniczy).                                                           | Stan zmienia się z **Wersja robocza** na **W trakcie przeglądu** i dalej na **Zatwierdzenie**, jeśli zamówienie zakupu nie zostanie odrzucone w procesie zatwierdzania. Zatwierdzone zamówienie zakupu jest rejestrowane jako wersja.           | 
| Zamówienie zakupu jest wysyłane do dostawcy.                                                            | Wersja jest rejestrowana w interfejsie współpracy z dostawcami, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**.      |
| Wprowadzasz kilka zmian, o które prosił dostawca, ręcznie lub za pomocą akcji w odpowiedzi, i w ten sposób aktualizujesz zamówienie zakupu.                                                            | Stan zostaje zmieniony z powrotem na **Wersja robocza**.     |
|Zamówienie zakupu jest wysyłane z powrotem do procesu zatwierdzania.                                                |  Stan zmienia się z **Wersja robocza** na **W trakcie przeglądu** i dalej na **Zatwierdzenie**, jeśli zamówienie zakupu nie zostanie odrzucone w procesie zatwierdzania. Alternatywnie można skonfigurować system w taki sposób, żeby modyfikacje w określonych polach nie wymagały ponownego zatwierdzania. W takim przypadku stan zmienia się najpierw na **Wersja robocza**, a następnie jest automatycznie aktualizowany do wartości **Zatwierdzone**. Zatwierdzone zamówienie zakupu jest rejestrowane jako nowa wersja.                                         |
|Wysyłasz nową wersję zamówienia zakupu do dostawcy.                                                |  Nowa wersja jest rejestrowana w interfejsie współpracy z dostawcami, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**.                                         |
|Dostawca zatwierdza nową wersję zamówienia zakupu.                                                |  Stan zmienia się na **Potwierdzone** automatycznie lub po otrzymaniu odpowiedzi od dostawcy i następnie ręcznym potwierdzeniu. |

## <a name="share-information-about-consignment-inventory"></a>Udostępnianie informacji o zapasach konsygnacyjnych
Jeśli używasz zapasów konsygnacyjnych, dostawcy mogą w interfejsie współpracy z dostawcami wyświetlać informacje na następujących stronach:

-   **Zamówienia zakupu zużywające zapasy konsygnacyjne** — Zamówienia zakupu dla zapasów konsygnacyjnych są generowane po zmianie właściciela zapasów z dostawcy na Twoją firmę. W tym samym momencie jest księgowany dokument przyjęcia produktów. Te zamówienia zakupu konsygnacyjnego są wyświetlane tylko na stronie **Zamówienia zakupu zużywające zapasy konsygnacyjne**. Nie są one umieszczane na stronie **Wszystkie potwierdzone zamówienia zakupu** w module **Portal współpracy z dostawcami**.
-   **Produkty odebrane z zapasów konsygnacyjnych** — Na tej stronie znajduje się lista wszystkich transakcji, w których własność produktów została przeniesiona z dostawcy na Twoją firmę. Dostawcy mogą używać tych informacji do fakturowania odbiorcy.
-   **Dostępne zapasy konsygnacyjne** — Na tej stronie są pokazane dostępne zapasy konsygnacyjne będące własnością dostawcy, które przyjęto do magazynu.





