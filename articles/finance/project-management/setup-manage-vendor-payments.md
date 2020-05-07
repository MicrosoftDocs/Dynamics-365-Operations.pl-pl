---
title: Konfigurowanie i używanie płatności dostawców płatnych po zapłaceniu
description: W tym temacie wyjaśniono, jak tworzyć warunki płatności po zapłaceniu (PWP), dzięki którym można zwolnić częściowe płatności dostawcy na podstawie płatności odbiorców.
author: RadhikaRS
manager: AnnBe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 390cec62d2790ed10892669e283f2283c6b8e686
ms.sourcegitcommit: 399f128d90b71bd836a1c8c0c8c257b7f9eeb39a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2020
ms.locfileid: "3284120"
---
# <a name="set-up-and-use-pay-when-paid-vendor-payments"></a>Konfigurowanie i używanie płatności dostawców płatnych po zapłaceniu

[!include [banner](../includes/banner.md)]

Po zaakceptowaniu dostawcy jako podwykonawcy, użytkownik może wstrzymać płatność dla dostawcy dopóki jego odbiorca nie dokona płatności za projekt. Aby obsługiwać ten scenariusz, należy zdefiniować warunki płatność po otrzymaniu zapłaty (pay-when-paid — PWP) podczas konfigurowania zamówienia zakupu z dostawcą.

Na przykład jeśli odbiorca zapłaci kwotę faktury projektu, użytkownik może zwolnić do zapłaty część lub całość kwoty faktury dostawcy. Można ustawić warunki PWP w taki sposób, że dostawca otrzymuje zapłatę po otrzymaniu od odbiorcy procentu powiązanej płatności. Jeśli po otrzymaniu częściowej płatności od odbiorcy, użytkownik może ręcznie zwolnić do zapłaty niektóre faktury dla powiązanego dostawcy.

W poniższym przykładzie proces jest używany podczas korzystania z warunków PWP.

## <a name="example"></a>Przykład

Twoja organizacja wyraża zgodę na dostarczenie klientowi 100 komputerów, na których zainstalowano oprogramowanie, za cenę 150,00 dolarów amerykańskich (USD) na komputer. Zatrudniany jest dostawca w celu dostarczenia komputerów, na których zainstalowano oprogramowanie. Zgodnie z umową odbiorca musi zatwierdzić jakość komputerów, zanim zapłaci organizacji. Zasady organizacji umożliwiają wstrzymanie płatności dostawcom do momentu zapłacenia przez odbiorcę. Dlatego też należy skonfigurować projekt w taki sposób, aby miał wartość procentową PWP o 100 procent.

Dostawca wysyła do użytkownika 100 komputerów, na których zainstalowano oprogramowanie, oraz fakturę na 10,000.00 USD. Ponieważ warunki PWP są skonfigurowane dla projektu, nie płaci się dostawcy po otrzymaniu tych komputerów. Zamiast tego użytkownik wysyła komputery do odbiorcy wraz z fakturą na 15,000.00. Odbiorca sprawdza komputery i zatwierdza jakości pełne kwoty faktury projektu.

Po otrzymaniu pełnej płatności od odbiorcy, płacisz dostawcy całą kwotę faktury 10 000,00.

## <a name="set-up-pwp-terms-for-a-project"></a>Konfigurowanie warunków ,,płatność po otrzymaniu zapłaty" PWP dla projektu

Konfigurując warunki PWP dla projektu, należy określić w procentach minimalną kwotę, jaką odbiorca musi zapłacić za projekt przed zapłaceniem dostawcy. Kwota progowa jest obliczana automatycznie na fakturach dla odbiorcy dla projektu. Wykonaj następujące kroki, aby ustawić procentowy próg dla warunków PWP.

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Projekty** \> **Wszystkie projekty**.
2. Znajdź i otwórz projekt, dla którego chcesz skonfigurować warunki PWP.
3. Na skróconej karcie **Umowy z dostawcami**, wybierz **Dodaj wiersz**.
3. W polu **Kod konta** wybierz jedną z następujących opcji:

    - **Tabela** – Warunki PWP mają zastosowanie do jednego dostawcy.
    - **Grupa** – Warunki PWP dotyczą wszystkich dostawców w grupie dostawców.
    - **Wszystkie** – Warunki PWP mają zastosowanie do wszystkich dostawców.

4. Jeśli w poprzednim kroku zaznaczono **Tabelę** lub **Grupę**, w polu **Dostawców/grup dostawców** wybierz dostawcę lub grupę dostawców, do których mają zastosowanie warunki PWP. Jeśli w poprzednim kroku zaznaczono opcję **Wszystkie**, nie można edytować pola **Dostawca/Grupa dostawców**.
5. Jeśli projekt ma także ustanowione warunki zatrzymania płatności dla dostawców w projekcie, w polu **Warunki zatrzymania płatności od dostawcy**, wybierz identyfikator reguły dla terminów zatrzymania płatności.
6. W polu **Wartość procentową progu PWP** wprowadź procentową wartość progową dla projektu. Wartość procentowa wprowadzona dla projektu wyznacza minimalną kwotę, jaką musi zapłacić klient zanim użytkownik dokona płatności dla dostawcy.

## <a name="create-a-po-that-has-pwp-terms"></a>Tworzenie zamówienia zakupu z warunkami PWP

Podczas księgowania faktury od dostawcy i w przypadku, gdy do dostawcy mają zastosowanie warunki PWP, te warunki są wyświetlane w wierszach zamówienia zakupu. Aby utworzyć zamówienie zakupu z warunkami PWP, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing** \> **Zamówienia zakupu** \> **Wszystkie zamówienia zakupu**.
2. W okienku akcji wybierz opcję **Nowy**. Następnie w oknie dialogowym **Tworzenie zamówienia zakupu** wprowadź wymagane informacje i kliknij przycisk **OK**.

    Można również otworzyć istniejącą pozycję PO na stronie listy **Wszystkie zamówienia zakupu**.

4. Na stronie **Zamówienie zakupu** na skróconej karcie **Wiersze zamówienia zakupu** przejrzyj szczegóły wiersza zamówienia zakupu dla dostawcy. Opcja **Płatność po otrzymaniu zapłaty** jest automatycznie zaznaczona, a wartość w polu **Wartość procentowa progu PWP** zostanie automatycznie skopiowana z pola **Wartość procentowa progu PWP** na stronie **Projekty**.
6. Jeśli do dostawcy dla wiersza zamówienia zakupu nie mają być stosowane warunki PWP, należy wyczyścić opcję **Płatność po otrzymaniu zapłaty**. W takim przypadku pole **Wartość procentowa progu PWP** dla wiersza zamówienia zakupu zostanie zresetowane do wartości 0 (zero).

## <a name="update-a-customer-payment-and-pay-the-vendor"></a>Uaktualnianie płatności od odbiorcy i dokonywanie płatności dla dostawcy

Gdy dostawca kończy pracę nad projektem i wysyła użytkownikowi fakturę, należy przejrzeć stan projektu i faktury odbiorcy, aby sprawdzić, czy spełnione zostały warunki PWP dla projektu. Jeżeli warunki PWP dla dostawcy zostały spełnione, można określić na podstawie płatności od odbiorcy za ten projekt, które wiersze na fakturze dostawcy są do zapłaty. Jeśli użytkownik zdecyduje się zapłacić dostawcy nawet wtedy, gdy warunki PWP nie zostały spełnione, można zastąpić warunki PWP na stronie **Faktury od dostawcy z opcją płać, gdy zapłacone**.

1. Przejdź do **Zarządzanie projektami i ich księgowanie** \> **Zapytania i raporty** \> **Zapytania o przechowywanie** \> **Faktury od dostawcy z opcją płać, gdy zapłacone**.
2. Na stronie **Faktury od dostawcy z opcją płać, gdy zapłacone** w polu wyszukiwania wprowadź wartości, aby znaleźć fakturę od dostawcy, którą chcesz przejrzeć, a następnie wybierz pozycję **Wyszukaj**.
3. Na skróconej karcie **Wiersze faktury od dostawcy** wybierz wiersze, które chcesz zmienić.
4. Jeśli dla wiersza faktury są spełnione warunki **Płatność po otrzymaniu zapłaty**, wybierz opcję **Zwolnij płatność dostawcy**. Opcja **Płatność po otrzymaniu zapłaty** jest wyczyszczona, a wartość pola **Gotowe do zapłaty** zostanie zmieniona na **Tak**.
