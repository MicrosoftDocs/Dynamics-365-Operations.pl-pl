---
title: "Współpraca z zewnętrznymi dostawcami"
description: "W tym temacie opisano, jak pracownicy działu zakupów mogą współpracować z zewnętrznymi dostawcami w celu wymiany informacji o zamówieniach zakupu i zapasach konsygnacyjnych."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: d585ae0716a4bd9c3531e8639cd7c6b3cab780ac
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-collaboration-with-external-vendors"></a>Współpraca z zewnętrznymi dostawcami

W tym temacie opisano, jak pracownicy działu zakupów mogą współpracować z zewnętrznymi dostawcami w celu wymiany informacji o zamówieniach zakupu i zapasach konsygnacyjnych.

Moduł **Portal współpracy z dostawcami** jest przeznaczony dla dostawców, którzy nie ma mają systemów elektronicznej wymiany danych (EDI) zintegrowanych z programem Microsoft Dynamics 365 for Operations. Umożliwia on dostawcom pracę z zamówieniami zakupu, fakturami i zapasami konsygnacyjnymi. W tym temacie opisano możliwości współpracy z zewnętrznymi dostawcami, którzy używają interfejsu współpracy z dostawcami do wykonywania operacji na zamówieniach zakupu i zapasach konsygnacyjnych. Omówiono także sposoby konfigurowania określonych dostawców do używania portalu współpracy z dostawcami oraz sposoby definiowania informacji wyświetlanych wszystkim dostawcom podczas odpowiadania na zamówienie zakupu. Aby uzyskać więcej informacji o tym, co zewnętrzni dostawcy mogą robić w interfejsie współpracy z dostawcami, zobacz [Współpraca dostawców z odbiorcami](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Aby uzyskać więcej informacji o tym, jak dostawcy mogą wykorzystywać portal współpracy z dostawcami w procesach fakturowania, zobacz [Obszar roboczy fakturowania w portalu współpracy z dostawcami](/dynamics365/operations/financials/accounts-payable/vendor-portal-invoicing-workspace). Aby uzyskać więcej informacji o inicjowaniu obsługi nowych użytkowników portalu współpracy z dostawcami, zobacz [Zarządzanie użytkownikami portalu współpracy z dostawcami](manage-vendor-collaboration-users.md).

## <a name="define-the-information-shown-to-vendors-when-they-respond-to-pos"></a>Definiowanie informacji wyświetlanych dostawcom podczas odpowiadania na zamówienia zakupu
Kiedy dostawcy odpowiadają na wysłane im zamówienie zakupu, widzą okno dialogowe, w którym muszą potwierdzić zamiar zaakceptowania zamówienia zakupu, odrzucenia go lub zaakceptowania ze zmianami. Informacje niezbędne do pokazania dostawcy w tym momencie mogą być specyficzne dla firmy, dlatego można określić tekst, który będzie wyświetlany w każdym z trzech komunikatów potwierdzenia. Na przykład tekst może informować dostawcę o następnych krokach w procesie lub o warunkach i postanowieniach.  

Aby określić tekst, który jest pokazywany w odpowiedzi na zamówienie zakupu:

1.  Otwórz stronę **Informacje dla dostawców odpowiadających na zamówienia zakupu**.
2.  Wybierz jeden z typów odpowiedzi.
3.  Kliknij przycisk **Edytuj**.
4.  W polu **Komunikat informacyjny** wprowadź informacje, które mają widzieć dostawcy.

Jeśli zachodzi konieczność dodania komunikatów w więcej niż jednym języku, utwórz różne komunikaty z kodami odpowiednich języków. Dostawca zobaczy komunikat w wersji językowej, której używa.

## <a name="set-the-vendor-collaboration-options-for-a-specific-vendor"></a>Ustawianie opcji współpracy z dostawcami dla określonego dostawcy
Ustawienia ogólne współpracy z dostawcami w programie Dynamics 365 for Operations są konfigurowane przez administratora. Na przykład administrator określa, które role zabezpieczeń są dostępne dla wszystkich dostawców, z którymi współpracujesz. Istnieją też pewne ustawienia, które mogą być różne dla różnych dostawców, oraz trzeba ustawić następujące opcje:

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

Zamówienia zakupu są przygotowywane w programie Dynamics 365 for Operations. Gdy organizacja producentów ma stan **zatwierdzone**, wysłać go do dostawcy przy użyciu ** Wyślij potwierdzenie ** akcji na **zamówienie zakupu** strony. Stan zamówienia zakupu zmieni się na **W trakcie analizy zewnętrznej**. Po wysłaniu zamówienia zakupu dostawca widzi je na stronie **Zamówienia zakupu do przeglądu** w interfejsie współpracy z dostawcami, gdzie może je zaakceptować, odrzucić lub zasugerować jego modyfikację. Dostawca może również dodać komentarze w celu przekazania informacji, np. o zmianach w zamówieniu zakupu. Jeśli chcesz zwrócić uwagę dostawcy na nowe zamówienie zakupu, możesz je wysłać e-mailem z systemu zarządzania drukowaniem.

### <a name="confirmation-and-acceptance-of-the-po-by-the-vendor"></a>Potwierdzanie i akceptacja zamówienia zakupu przez dostawcę

Gdy dostawca zaakceptuje zamówienie zakupu, może ono zostać potwierdzone automatycznie lub wymagać ręcznego potwierdzenia. To zależy od tego, czy ** aktywacji dostawcy ** pole jest ustawione na **Active (zamówienia zakupu jest potwierdzone auto)** dla dostawcy lub na **Active (zamówienia zakupu nie jest potwierdzone auto)**.  

W poniższej tabeli przedstawiono typową wymianę informacji, w zależności od odpowiedzi dostawcy na wysłanie mu zamówienia zakupu do potwierdzenia.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Odpowiedź dostawcy</strong></td>
<td><strong>Wynik</strong></td>
</tr>
<tr class="even">
<td>Dostawca <strong>akceptuje</strong> zamówienie. W programie Dynamics 365 for Operations skonfigurowano automatyczne potwierdzanie zamówień zakupu po ich zaakceptowaniu przez dostawców.</td>
<td>Stan zamówienia jest zaktualizowany do <strong>Potwierdzone</strong>. Jeśli z jakiegoś powodu nie można zaktualizować zamówienia, odpowiedź dostawcy i tak zostanie zarejestrowana jako <strong>Zaakceptowane</strong>, ale zamówienie zakupu będzie nadal miało stan <strong>W trakcie analizy zewnętrznej</strong>.</td>
</tr>
<tr class="odd">
<td>Dostawca <strong>akceptuje</strong> zamówienie. W programie Dynamics 365 for Operations nie skonfigurowano automatycznego potwierdzania zamówień zakupu po ich zaakceptowaniu przez dostawców.</td>
<td>Odpowiedź dostawcy zostanie zarejestrowana jako <strong>Zaakceptowane</strong>, ale zamówienie zakupu będzie nadal miało stan <strong>W trakcie analizy zewnętrznej</strong>.</td>
</tr>
<tr class="even">
<td>Dostawca <strong>odrzuca</strong> zamówienie.</td>
<td>Odpowiedź dostawcy zostanie zarejestrowana jako <strong>Odrzucone</strong>, a zamówienie zakupu będzie nadal miało stan <strong>W trakcie analizy zewnętrznej</strong>. Odrzucenie jest odbierane razem z notatkami dostawcy.</td>
</tr>
<tr class="odd">
<td>Dostawca <strong>akceptuje zamówienia ze zmianami</strong>. Zmiany sugerowane są na poziomie wiersza. Istnieje możliwość zaakceptowania lub odrzucenia poszczególnych wierszy. Inne możliwe zmiany:
<ul>
<li>Zmiana dat lub ilości.</li>
<li>Podział wierszy dla różnych dat dostawy lub ilości.</li>
<li>Zastąpienie towaru.</li>
</ul>
Informacje o cenach i opłatach nie mogą być zmieniane przez dostawcę. Sugestie dotyczące zmian mogą być dokonywane za pomocą notatek.</td>
<td>Odpowiedź dostawcy jest rejestrowana jako <strong>zaakceptowane zmiany</strong>, <strong></strong>i pozostaje w stanie PO <strong>w zewnętrznych Przegląd</strong>.</td>
</tr>
</tbody>
</table>

Można użyć **zamówienia zakupu****przygotowania** obszaru roboczego monitorowanie którym POs dostawca odpowiedział na. Ten obszar roboczy zawiera dwie listy, które zawierają zamówień zakupu ze stanem **w zewnętrznych Przegląd**:

-   W trakcie przeglądu zewnętrznego (wymaga wykonania akcji).
-   W trakcie analizy zewnętrznej, oczekuje na odpowiedź dostawcy.

### <a name="changing-a-po"></a>Zmiana zamówienia zakupu

Jeśli trzeba zmienić zamówienie zakupu, na które już odpowiedziano, należy wysłać nowe zamówienie zakupu do dostawcy. Nowe zamówienie będzie miało sufiks wersji wskazujący, że jest to zmodyfikowana wersja zamówienia zakupu, które zostało wcześniej przekazane. Na stronie **Historia potwierdzeń zamówień zakupu przez dostawcę** Ty i Twoi dostawcy możecie śledzić historię każdego zamówienia. Poprzednio potwierdzona wersja zamówienia zakupu pozostaje na liście potwierdzonych zamówień zakupu do czasu potwierdzenia nowego zamówienia zakupu.

### <a name="cancelling-a-po"></a>Anulowanie zamówienia zakupu

Po anulowaniu zamówienia zakupu jego stan zmienia się na **Zatwierdzone**. Zamówienie zakupu trzeba odesłać dostawcy za pośrednictwem portalu, tak aby dostawca mógł potwierdzić lub odrzucić anulowanie. Po potwierdzeniu anulowania zamówienie zakupu pojawi się na liście potwierdzonych zamówień zakupu dostawcy jako **Anulowane**.

### <a name="adding-attachments-to-a-po"></a>Dodawanie załączników do zamówienia zakupu

Za pomocą systemu zarządzania dokumentami można do zamówienia zakupu dodawać załączniki, takie jak pliki, obrazy i notatki. Załączniki dodane z ograniczeniem typu **Zewnętrzne** będą widoczne dla dostawcy po wysłaniu mu zamówienia zakupu.

## <a name="purchase-order-statuses-and-versions"></a>Stan i wersje zamówienia zakupu
W tej sekcji opisano różne stany, które może przyjmować zamówienie zakupu do momentu potwierdzenia, oraz wyjaśniono, w którym punkcie nowe wersje zamówienia zakupu są udostępniane dostawcy. Istnieją różnice w tym, w zależności od tego, czy używasz zarządzania zmianami dla zamówień zakupu. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Wersji i stany, jeśli nie jest używane zarządzanie zmianami

W poniższej tabeli pokazano przykład zmian stanu i wersji, przez jakie może przechodzić zamówienie zakupu.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Akcja**                                                               | **Stan i wersja**                                                                                                                                       |
| Pierwotna wersja zamówienia zakupu jest tworzona w programie Dynamics 365 for Operations. | Ma ona stan **Zatwierdzone**.                                                                                                                                  |
| Zamówienie zakupu jest wysyłane do dostawcy.                                            | Wersja jest rejestrowana w interfejsie współpracy z dostawcami, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**.                                          |
| Dostawca wysyła odpowiedź **Zaakceptowano ze zmianami**.                  | Stan to nadal **W trakcie analizy zewnętrznej**.                                                                                                                  |
| Wprowadzasz kilka zmian, o które prosił dostawca.                  | Stan zostaje zmieniony na **Zatwierdzone**.                                                                                                                        |
| Wysyłasz nową wersję zamówienia zakupu do dostawcy.                        | Nowa wersja jest rejestrowana w interfejsie współpracy z dostawcami, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**.                                      |
| Dostawca akceptuje nową wersję zamówienia zakupu.                            | Stanem jest nadal **W trakcie analizy zewnętrznej **, chyba że dostawca jest skonfigurowany do automatycznego ustawiania zamówienia zakupu do stanu **Potwierdzone** w momencie akceptacji. |

Dostawcy nie muszą potwierdzać zamówień zakupu w interfejsie współpracy z dostawcami. Zamiast tego mogą również wysłać wiadomość e-mail lub zawiadomić o przyjęciu zamówienia zakupu przez inne kanały komunikacji. Wtedy można potwierdzić zamówienie ręcznie w programie Dynamics 365 for Operations. W takim przypadku zobaczysz ostrzeżenie informujące, że trwa potwierdzanie zamówienia, nawet jeśli nie ma odpowiedzi od dostawcy. Zamówienie zakupu pojawi się wtedy w historii potwierdzeń jako otwarte zamówienie potwierdzone, które nie ma żadnych odpowiedzi. Dostawca nie będzie już mógł potwierdzić ani odrzucić zamówienia zakupu.  

**Uwaga:** Wersją zamówienia zakupu dostępną dla innych procesów w programie Dynamics 365 for Operations jest zawsze najnowsza wersja, nawet jeśli jeszcze nie została zarejestrowana w interfejsie współpracy z dostawcami.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Wersji i stany, jeśli jest używane zarządzanie zmianami

Jeśli dla zamówień zakupu włączono funkcję zarządzania zmianami, zamówienie przejdzie przez przepływ pracy zatwierdzania aż do osiągnięcia stanu **Zatwierdzone**. Ten proces nie jest widoczny dla dostawcy.  

W poniższej tabeli pokazano przykład zmian stanu i wersji, przez jakie może przechodzić zamówienie zakupu przy włączonej opcji zarządzania zmianami. Wersja jest rejestrowana po zatwierdzeniu zamówienia, a nie wtedy, gdy zamówienie zakupu zostanie wysłane do dostawcy lub potwierdzone.

|                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Akcja**                                                                                                    | **Stan i wersja**                                                                                                                                                                                                                                                                                                                                                                      |
| Pierwotna wersja zamówienia zakupu jest tworzona w programie Dynamics 365 for Operations.                                      | Stan to **Wersja robocza**.                                                                                                                                                                                                                                                                                                                                                                    |
| Zamówienie zakupu jest wysyłane do procesu zatwierdzania (jest to proces wewnętrzny, w którym dostawca nie uczestniczy). | Stan zmienia się z **Wersja robocza** na **W trakcie przeglądu** i dalej na **Zatwierdzenie**, jeśli zamówienie zakupu nie zostanie odrzucone w procesie zatwierdzania. Zatwierdzone zamówienie zakupu jest rejestrowane jako wersja.                                                                                                                                                                                                                     |
| Zamówienie zakupu jest wysyłane do dostawcy.                                                                                  | Wersja jest rejestrowana w interfejsie współpracy z dostawcami, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**.                                                                                                                                                                                                                                                                       |
| Wprowadzasz kilka zmian, o które prosił dostawca.                                                       | Stan zostaje zmieniony z powrotem na **Wersja robocza**.                                                                                                                                                                                                                                                                                                                                                    |
| Zamówienie zakupu jest wysyłane z powrotem do procesu zatwierdzania.                                                            | Stan zmienia się z **Wersja robocza** na **W trakcie przeglądu** i dalej na **Zatwierdzenie**, jeśli zamówienie zakupu nie zostanie odrzucone w procesie zatwierdzania. Alternatywnie można skonfigurować system w taki sposób, żeby modyfikacje w określonych polach nie wymagały ponownego zatwierdzania. W takim przypadku stan zmienia się najpierw na **Wersja robocza**, a następnie jest automatycznie aktualizowany do wartości **Zatwierdzone**. Zatwierdzone zamówienie zakupu jest rejestrowane jako nowa wersja. |
| Wysyłasz nową wersję zamówienia zakupu do dostawcy.                                                             | Nowa wersja jest rejestrowana w interfejsie współpracy z dostawcami, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**.                                                                                                                                                                                                                                                                   |
| Dostawca zatwierdza nową wersję zamówienia zakupu.                                                                | Stan zmienia się na **Potwierdzone** automatycznie lub po otrzymaniu odpowiedzi od dostawcy i następnie ręcznym potwierdzeniu.                                                                                                                                                                                                                                                     |

## <a name="share-information-about-consignment-inventory"></a>Udostępnianie informacji o zapasach konsygnacyjnych
Jeśli używasz zapasów konsygnacyjnych, dostawcy mogą w interfejsie współpracy z dostawcami wyświetlać informacje na następujących stronach:

-   **Zamówienia zakupu zużywające zapasy konsygnacyjne** — Zamówienia zakupu dla zapasów konsygnacyjnych są generowane po zmianie właściciela zapasów z dostawcy na Twoją firmę. W tym samym momencie jest księgowany dokument przyjęcia produktów. Te zamówienia zakupu konsygnacyjnego są wyświetlane tylko na stronie **Zamówienia zakupu zużywające zapasy konsygnacyjne**. Nie są one umieszczane na stronie **Wszystkie potwierdzone zamówienia zakupu** w module **Portal współpracy z dostawcami**.
-   **Produkty odebrane z zapasów konsygnacyjnych** — Na tej stronie znajduje się lista wszystkich transakcji, w których własność produktów została przeniesiona z dostawcy na Twoją firmę. Dostawcy mogą używać tych informacji do fakturowania odbiorcy.
-   **Dostępne zapasy konsygnacyjne** — Na tej stronie są pokazane dostępne zapasy konsygnacyjne będące własnością dostawcy, które przyjęto do magazynu.



