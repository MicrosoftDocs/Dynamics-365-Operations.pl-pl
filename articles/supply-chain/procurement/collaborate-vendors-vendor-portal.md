---
title: Współpraca z dostawcami za pomocą portalu dostawców
description: W tym temacie wyjaśniono, jak pracownicy działu zakupów mogą używać portalu dostawców do współpracy z dostawcami zewnętrznymi w trakcie procesu potwierdzenia zamówień zakupu. Informacje te dotyczą tylko wersji systemu Dynamics AX z lutego i maja 2016 roku.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3bb30ddffb86c7083f40863c0c336fc5f65ce8f5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248987"
---
# <a name="collaborate-with-vendors-by-using-the-vendor-portal"></a>Współpraca z dostawcami za pomocą portalu dostawców

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak pracownicy działu zakupów mogą używać portalu dostawców do współpracy z dostawcami zewnętrznymi w trakcie procesu potwierdzenia zamówień zakupu. Informacje te dotyczą tylko wersji systemu Dynamics AX z lutego i maja 2016 roku.

Informacje zawarte w tym temacie dotyczą tylko wersji systemu Dynamics AX z lutego i maja 2016 roku. Aby uzyskać więcej informacji o funkcjonalności nowego portalu współpracy z dostawcami, zobacz [Używanie portalu współpracy z dostawcami do obsługi współpracy z dostawcami zewnętrznymi](vendor-collaboration-work-external-vendors.md).  

Portal dostawców jest przeznaczony dla dostawców, którzy nie posiadają interfejsów elektronicznej wymiany danych (EDI) z systemem Microsoft Dynamics AX na potrzeby wymiany informacji o zamówieniach zakupu (PO). Portal umożliwia pracownikom działu zakupów wysyłanie zamówień zakupu do dostawcy, a następnie odbieranie odpowiedzi o potwierdzeniu lub odrzuceniu bezpośrednio w systemie Dynamics AX.  

Proces można skonfigurować tak, aby potwierdzenie od dostawcy automatycznie potwierdzało zamówienie. W takim przypadku wykonanie kolejnych kroków jest konieczne tylko od czasu do czasu, gdy zamówienie zostanie odrzucone lub potwierdzenie dostawcy jest zarejestrowane jako odpowiedź, ale stan zamówienia zakupu nie został zaktualizowany na **Potwierdzone** z powodu błędu w procesie potwierdzania.

## <a name="po-confirmation-and-rejection"></a>Potwierdzanie i odrzucanie zamówienia zakupu
Zamówienia zakupu są przygotowywane w systemie Dynamics AX. Jeśli masz zamówienia zakupu o stanie **Zatwierdzone**, wysyłasz je do dostawcy poprzez wygenerowanie żądania potwierdzenia. Jeśli chcesz zwrócić uwagę dostawcy na nowe zamówienie zakupu, możesz je wysłać e-mailem z systemu zarządzania drukowaniem. Zamówienie zakupu pojawi się w portalu dostawców i zawiera opcję pozwalającą dostawcy je potwierdzić lub odrzucić. Dostawca może również dodać komentarze w celu przekazania informacji, np. o zmianach w zamówieniu zakupu.  

W portalu dostawców dostawca widzi wiersze zamówienia. Wiersze te zawierają informacje takie jak zewnętrzny numer produktu, wymiary, ceny, ilość, data dostawy i adres dostawy. Dostawa może wygenerować raport pokazujący informacje o zamówieniu zakupu oraz łączną cenę. Opłaty ponoszone przez dostawcę są wyświetlane, gdy dostawca kliknie przycisk **Opłaty** w nagłówku lub w wierszach. Dostawca może zaimportować informacje o zamówieniu zakupu do własnego systemu przy użyciu funkcji **Eksportuj do programu Excel**.  

W poniższej tabeli przedstawiono typową wymianę informacji, zależną od odpowiedzi dostawcy na wysłanie mu zamówienia zakupu do potwierdzenia.

| Typ odpowiedzi                                                                                                  | Wynik                                                                                                                                                                                                                                                                                          |
|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dostawca potwierdził zamówienie. W systemie skonfigurowano automatyczne potwierdzanie zamówień zakupu po ich potwierdzeniu przez dostawców.    | Stan zamówienia jest zaktualizowany do **Potwierdzone**. Jeśli z jakiegoś powodu nie można zaktualizować zamówienia, odpowiedź dostawcy i tak zostanie zarejestrowana jako **Potwierdzone**, ale zamówienie zakupu będzie nadal miało stan **W trakcie analizy zewnętrznej**.                                                                       |
| Dostawca potwierdził zamówienie. W systemie nie skonfigurowano automatycznego potwierdzania zamówień zakupu po ich potwierdzeniu przez dostawców. | Odpowiedź dostawcy zostanie zarejestrowana jako **Potwierdzone**, ale zamówienie zakupu będzie nadal miało stan **W trakcie analizy zewnętrznej**.                                                                                                                                                                                      |
| Dostawca odrzucił zamówienie.                                                                                     | Odpowiedź dostawcy zostanie zarejestrowana jako **Odrzucone**, a zamówienie zakupu będzie nadal miało stan **W trakcie analizy zewnętrznej**. Odrzucenie jest odbierane wraz z przyczyną i propozycją zmiany, na przykład na inną datę dostawy. Aktualizujesz zamówienia zakupu, a następnie wysyłasz nową wersję do potwierdzenia. |

## <a name="changes-to-a-po"></a>Zmiany w zamówieniu zakupu
Kiedy trzeba zmienić zamówienie zakupu, które zostało już potwierdzone, można wysłać do dostawcy nowe zamówienie zakupu w portalu. Nowe zamówienie będzie miało sufiks wersji wskazujący, że jest to zmodyfikowana wersja zamówienia zakupu, które zostało wcześniej przekazane. Portal dostawców umożliwia dostawcom śledzenie historii każdego zamówienia. Poprzednio potwierdzona wersja zamówienia zakupu pozostanie na liście potwierdzonych zamówień zakupu do czasu potwierdzenia nowego zamówienia zakupu.  

Po anulowaniu zamówienia zakupu jego stan zmienia się z powrotem na **Zatwierdzone**. Zamówienie zakupu trzeba odesłać dostawcy za pośrednictwem portalu, tak aby dostawca mógł potwierdzić lub odrzucić anulowanie. Po potwierdzeniu anulowania zamówienie zakupu pojawi się na liście potwierdzonych zamówień zakupu dostawcy jako **Anulowane**.

## <a name="versions-status-transitions-and-change-management"></a>Wersje, zmiany stanu i zarządzanie zmianami
Po wysłaniu zamówienia zakupu do dostawcy zostaje ono zarejestrowane w systemie jako określona wersja zamówienia zakupu, a jego stan zmienia się z **Zatwierdzone** na **W trakcie analizy zewnętrznej**. W przypadku późniejszego wprowadzenia zmian w zamówieniu zakupu zostanie utworzona nowa wersja zamówienia zakupu, a stan zmieni się z powrotem na **Zatwierdzone** (lub **Wersja robocza**, jeżeli została włączona opcja zarządzania zmianami).  

W poniższej tabeli pokazano przykład zmian stanu i wersji, przez jakie może przechodzić zamówienie zakupu.

| Akcja                                                   | Stan i wersja                                                                                    |
|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| Pierwotna wersja zamówienia zakupu jest tworzona w systemie Dynamics AX. | Ma ona stan **Zatwierdzone**.                                                                           |
| Zamówienie zakupu jest wysyłane do portalu dostawców.                     | Wersja jest rejestrowana w portalu dostawców, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**.    |
| Wprowadzasz kilka zmian, o które prosił dostawca.  | Stan zostaje zmieniony z powrotem na **Zatwierdzone**.                                                            |
| Wysyłasz nową wersję zamówienia zakupu do portalu dostawców. | Nowa wersja jest rejestrowana w portalu dostawców, a jej stan zmienia wartość na **W trakcie analizy zewnętrznej**. |
| Dostawca zatwierdza nową wersję zamówienia zakupu.           | Stan zostaje zmieniony na **Potwierdzone**.                                                                |

Aby wyświetlić wersje zamówienia zakupu wysłane do dostawcy oraz odpowiedzi dostawcy, w oknie zamówienia zakupu wybierz kolejno polecenia **Arkusze** &gt; **Żądania potwierdzenia**.  

Zamówienia, które zostały wysłane do dostawcy w celu udzielenia odpowiedzi i mają stan **W trakcie analizy zewnętrznej**, pojawią się na liście **Zamówienia zakupu zostały wysłane do portalu dostawców, oczekiwanie na odpowiedź** lub liście **Zamówienia zakupu zostały wysłane do portalu dostawców, odpowiedź wymaga akcji**. Jeśli wprowadzisz zmiany w zamówieniu, które zostało wysłane do dostawcy, co powoduje zmianę stanu zamówienia na **Zatwierdzone**, zamówienie nie będzie się już pojawiało na tych listach. Aby sprawdzić, czy była uprzednio odpowiedź od dostawcy na zamówienia, kliknij kolejno opcje **Arkusze** &gt; **Żądania potwierdzenia**.  

Dostawcy nie muszą potwierdzać zamówień zakupu w portalu dostawców. Zamiast tego mogą również wysłać wiadomość e-mail lub zawiadomić o przyjęciu zamówienia zakupu przez inne kanały komunikacji. Wtedy można potwierdzić zamówienie ręcznie w systemie Dynamics AX. W takim przypadku zobaczysz ostrzeżenie informujące, że trwa potwierdzanie zamówienia, nawet jeśli nie ma odpowiedzi od dostawcy. Zamówienie zakupu pojawi się wtedy w historii potwierdzeń w portalu dostawców jako otwarte zamówienie potwierdzone, które nie ma żadnych odpowiedzi. Ponadto dostawca nie będzie już mógł potwierdzić ani odrzucić zamówienia zakupu.  

**Uwaga:** Wersją zamówienia zakupu dostępną dla innych procesów w systemie Dynamics AX jest zawsze najnowsza wersja, nawet jeśli jeszcze nie została zarejestrowana.

### <a name="change-management"></a>Zarządzanie zmianami

Jeśli dla zamówienia zakupu włączono funkcję zarządzania zmianami, zamówienie przejdzie przez przepływ pracy zatwierdzania aż do osiągnięcia stanu **Zatwierdzone**. Ten proces nie jest widoczny dla dostawcy.  

Jeśli dla zamówienia zakupu jest włączona funkcja zarządzania zmianami, wersja jest rejestrowana po zatwierdzeniu zamówienia, a nie wtedy, gdy zamówienie zakupu zostanie wysłane do dostawcy lub potwierdzone.  

W poniższej tabeli pokazano przykład zmian stanu i wersji, przez jakie może przechodzić zamówienie zakupu przy włączonej opcji zarządzania zmianami.


|                                                    Akcja                                                     |                                                                                                                                                                                                                      Stan i wersja                                                                                                                                                                                                                      |
|---------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           Pierwotna wersja zamówienia zakupu jest tworzona w systemie Dynamics AX.                            |                                                                                                                                                                                                            Stan to <strong>Wersja robocza</strong>.                                                                                                                                                                                                             |
| Zamówienie zakupu jest wysyłane do procesu zatwierdzania (jest to proces wewnętrzny, w którym dostawca nie uczestniczy). |                                                                                                                        Stan zmienia się z <strong>Wersja robocza</strong> na <strong>W trakcie przeglądu</strong> i dalej na <strong>Zatwierdzenie</strong>, jeśli zamówienie zakupu nie zostanie odrzucone w procesie zatwierdzania. Zatwierdzone zamówienie zakupu jest rejestrowane jako wersja.                                                                                                                        |
|                                      Następnie zamówienie zakupu trafia na portal dostawców                                      |                                                                                                                                                                      Wersja jest rejestrowana w portalu dostawców, a jej stan zmienia wartość na <strong>W trakcie analizy zewnętrznej</strong>.                                                                                                                                                                       |
|                            Wprowadzasz kilka zmian, o które prosił dostawca.                            |                                                                                                                                                                                                    Stan zostaje zmieniony z powrotem na <strong>Wersja robocza</strong>.                                                                                                                                                                                                     |
|                              Zamówienie zakupu jest wysyłane z powrotem do procesu zatwierdzania.                               | Stan zmienia się z <strong>Wersja robocza</strong> na <strong>W trakcie przeglądu</strong> i dalej na <strong>Zatwierdzenie</strong>, jeśli zamówienie zakupu nie zostanie odrzucone w procesie zatwierdzania. Alternatywnie można skonfigurować system w taki sposób, żeby modyfikacje w określonych polach nie wymagały ponownego zatwierdzania. W takim przypadku stan zmienia się najpierw na <strong>Wersja robocza</strong>, a następnie jest automatycznie aktualizowany do wartości <strong>Zatwierdzone</strong>. Zatwierdzone zamówienie zakupu jest rejestrowane jako nowa wersja. |
|                           Wysyłasz nową wersję zamówienia zakupu do portalu dostawców.                            |                                                                                                                                                                    Nowa wersja jest rejestrowana w portalu dostawców, a jej stan zmienia wartość na <strong>W trakcie analizy zewnętrznej</strong>.                                                                                                                                                                     |
|                                Dostawca zatwierdza nową wersję zamówienia zakupu.                                 |                                                                                                                                                     Stan zmienia się na <strong>Potwierdzone</strong> automatycznie lub po otrzymaniu odpowiedzi od dostawcy i następnie ręcznym potwierdzeniu.                                                                                                                                                     |

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Konfiguracja zabezpieczeń dla użytkowników portalu współpracy z dostawcami](configure-security-vendor-portal-users.md)

[Obszar roboczy fakturowania w portalu współpracy z dostawcami](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md)



