---
title: Przetwarzanie wsadowe alertów
description: Ten temat zawiera ogólne informacje o przetwarzaniu wsadowym alertów.
author: tjvass
manager: AnnBe
ms.date: 09/10/2010
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: d57586cb18c581e4a462d93a64a88310e251a7af
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798603"
---
# <a name="batch-processing-of-alerts"></a>Przetwarzanie wsadowe alertów

[!include [banner](../includes/banner.md)]

Alerty są przetwarzane za pomocą funkcji przetwarzania wsadowego. Funkcja przetwarzania wsadowego musi zostać skonfigurowana przed rozpoczęciem procesu i dostarczania alertów.

Funkcja przetwarzania wsadowego obsługuje dwa typy zdarzeń:

- Zdarzenia wywoływane przez zdarzenia zależne od zmian. Te zdarzenia są także nazywane zdarzeniami tworzenia/usuwania i aktualizacji.
- Zdarzenia wywoływane przez terminy.

Istnieje możliwość skonfigurowania przetwarzania wsadowego dla każdego typu zdarzenia.

## <a name="batch-processing-for-change-based-events"></a>Przetwarzanie wsadowe zdarzeń zależnych od zmian

System odczytuje wszystkie zdarzenia zależne od zmian, które nastąpiły od czasu ostatniego uruchomienia przetwarzania wsadowego. Zdarzenia zależne od zmian zawierają aktualizacje pól, usuwanie rekordów i tworzenie rekordów. Te zdarzenia są porównywane z warunkami zdefiniowanymi w regułach alertów. Jeżeli zdarzenie jest zgodne z warunkami w regule, proces przetwarzania wsadowego generuje alert.

### <a name="frequency-for-change-based-events"></a>Częstotliwość dla zdarzeń zależnych od zmian

W przypadku zdarzeń zależnych od zmian można zdefiniować zadanie wsadowe, które uruchamia przetwarzanie zdarzenia wkrótce po zalogowaniu zdarzenia w systemie. Jeśli skonfigurujesz częstsze wykonywanie zadania wsadowego, użytkownicy będą otrzymywali alerty wcześniej po nastąpieniu zmian. Jednak duża częstotliwość przetwarzania wsadowego może negatywnie wpływać na wydajność systemu.

Z drugiej strony zadanie wsadowe, które powtarza się rzadziej i zostało zaplanowane na okresy, gdy obciążenie systemu jest niskie, może poprawiać ogólną wydajność działania systemu. Jednak zbyt niska częstotliwość przetwarzania wsadowego może nie spełniać wymagań użytkowników w kwestii sprawnego otrzymywania alertów.

Dlatego podczas konfigurowania częstotliwości przetwarzania wsadowego zdarzeń zależnych od zmian należy znaleźć równowagę między terminowością dostarczania alertów a działaniem całego systemu. Kwestie te nabierają znaczenia wraz ze wzrostem liczby użytkowników tworzących reguły alertów. Częstotliwość nie wpływa na liczbę zdarzeń, które są przetwarzane przez system. Jednak im więcej użytkowników tworzy reguły, tym więcej testów przeprowadza proces. Ten rodzaj wymiany danych może wpływać na wydajność systemu.

#### <a name="the-risks-of-low-batch-frequency"></a>Zagrożenia związane z niską częstotliwością przetwarzania wsadowego

Jeżeli skonfigurujesz niską częstotliwość przetwarzania wsadowego zdarzeń zależnych od zmian, dane istotne dla warunków w regułach alertów mogą ulec zmianie przed rozpoczęciem przetwarzania. W efekcie możesz nie otrzymać części alertów.

Na przykład utworzony alert, który ma być wywoływany po zdarzeniu **zmiana danych kontaktowych odbiorcy** przy warunku **odbiorca = BB**. Innymi słowy zdarzenie to jest rejestrowane przez proces po zmianie osoby kontaktowej u odbiorcy BB. Jednak system przetwarzania wsadowego skonfigurowano w taki sposób, że przetwarzanie wsadowe odbywa się rzadziej, niż wprowadzanie danych. Jeśli nazwa odbiorcy zmienia się z **BB** na **AA**, zanim nastąpi przetwarzanie zdarzenia, dane w bazie danych przestaną pasować do warunku w regule **odbiorca = BB**. W związku z tym po zakończeniu przetwarzania zdarzenia nie zostanie wygenerowany żaden alert.

### <a name="set-up-processing-for-change-based-alerts"></a>Konfigurowanie przetwarzania alertów zależnych od zmian

1. Wybierz kolejno opcje **Administrowanie systemem** &gt; **Zadania okresowe** &gt; **Alerty** &gt; **Alerty na podstawie zmian**.
2. W oknie dialogowym **Alerty na podstawie zmian** wprowadź odpowiednie informacje.

## <a name="batch-processing-for-due-date-events"></a>Przetwarzanie wsadowe zdarzeń zależnych od terminów

System wykrywa wszystkie zdarzenia wywołane przez terminy wykonania i porównuje je z warunkami zdefiniowanymi w regułach alertów. Proces przetwarzania wsadowego generuje alert, jeżeli zdarzenie jest zgodne z warunkami w regule.

### <a name="frequency-for-due-date-events"></a>Częstotliwość dla zdarzeń zależnych od terminów

W przypadku zdarzeń zależnych od terminów można zdefiniować zadania wsadowe, które będą uruchamiane w nocy lub w określonych porach dnia w celu zrównoważenia obciążenia systemu. Zalecamy takie skonfigurowanie zadania wsadowego, aby było wykonywane co najmniej raz dziennie. Jeżeli alerty mają być wysyłane jak najszybciej, skonfiguruj przetwarzanie wsadowe tak, aby następowało niezwłocznie po zmianie daty systemowej. Jeżeli chcesz generować alerty o zdarzeniach zależnych od terminów, które nastąpiły już po zakończeniu przetwarzania alertów przez zadanie wsadowe, można uruchomić zadanie wsadowe ponownie danego dnia.

Na przykład zadanie wsadowe wykonano w określonym dniu. Następnie tworzysz zamówienie zakupu z terminem wykonania, który powinien wywoływać alert tego samego dnia. Aby otrzymać alert w danym dniu, należy uruchomić zadanie wsadowe ponownie po utworzeniu zamówienia zakupu. Jednak jeżeli zadanie wsadowe nie zostanie uruchomione ponownie danego dnia, zadanie wsadowe w kolejnym dniu wykryje wszystkie zdarzenia zależne od terminu wykonania, które nie zostały przetworzone w poprzednich dniach.

> [!NOTE]
> Nawet jeżeli przetwarzanie wsadowe jest uruchamiane więcej niż raz dziennie, alerty nie powtarzają się dla tych samych zdarzeń zależnych od terminów i tych samych warunków. Alerty są generowane tylko dla dat, które stały się terminami wykonania na skutek zmian zaistniałych w systemie po zakończeniu ostatniego zadania wsadowego.

### <a name="batch-processing-window"></a>Okno przetwarzania wsadowego

Przetwarzanie reguł alertów w firmie można zatrzymać z kilku powodów. Przyczyną może być na przykład urlop, błędy systemu lub inne problemy uniemożliwiające wykonywanie zadań wsadowych przez pewien czas.

Aby zapobiec sytuacji, w której alerty zależne od terminów wykonania stają się przestarzałe, ponieważ zadanie wsadowe nie było uruchamiane przez kilka dni, można skonfigurować okno czasowe przetwarzania wsadowego. Okno czasowe przetwarzania wsadowego może służyć do zablokowania wykonywania zadania wsadowego przez określoną liczbę dni.

Jeśli skonfigurujesz okno czasowe przetwarzania wsadowego, alert zostanie wysłany po przetworzeniu reguły alertu nawet wtedy, gdy alert przekroczy limit czasu zdefiniowany w kryteriach terminu wykonania. Alert będzie wysyłany aż do zakończenia okresu zdefiniowanego przez ten limit czasu powiększony o okno czasowe przetwarzania wsadowego. Z chwilą, gdy okres przekroczy wartość zdefiniowaną przez ten limit czasu powiększony o okno czasowe przetwarzania wsadowego alert przestanie być wysyłany.

### <a name="set-up-processing-for-due-date-alerts"></a>Konfigurowanie przetwarzania alertów zależnych od terminu

1. Wybierz kolejno opcje **Administrowanie systemem** &gt; **Zadania okresowe** &gt; **Alerty** &gt; **Alerty terminów**.
2. W oknie dialogowym **Alerty terminów** wprowadź odpowiednie informacje.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]