---
title: Daty wystawienia faktury przez sprzedawcę
description: W tym artykule opisano daty, które są widoczne na fakturach dostawcy. Wyjaśnia również, jak skonfigurować system, aby automatycznie dostosowywał datę księgowania.
author: sunfzam
ms.date: 2/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 943a84407d022c2c05bc534a35a2b5d44a94653e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876420"
---
# <a name="vendor-invoice-dates"></a>Daty wystawienia faktury przez sprzedawcę

[!include [banner](../includes/banner.md)]

W tym artykule opisano daty, które są widoczne na fakturach dostawcy. Wyjaśnia również, jak skonfigurować system, aby automatycznie dostosowywał datę księgowania.

Na stronie **szczegółowa faktura oczekującego dostawcy** w nagłówku faktury znajdują się cztery daty: data otrzymania faktury, data faktury, data zaksięgowania oraz data wymagalności. Podczas tworzenia faktury sprzedawcy domyślnie wprowadzane są następujące daty:

- **Data otrzymania faktury** — w tym polu jest ustawiona bieżąca data systemowa.
- **Data księgowania faktury** — w tym polu jest ustawiona bieżąca data systemowa. 
- **Data należności** — Data w tym polu jest obliczana na podstawie daty księgowania i warunków płatności.
- **Data faktury** — domyślnie to pole jest puste. Można jednak zmienić jego wartość. W takim przypadku data w polu **Data należności** jest przeliczana na podstawie daty faktury i warunków płatności.

Zdarza się, że faktura dostawcy może być w stanie oczekiwania jeszcze przez długi czas po zamknięciu okresu. Kiedy jest on gotowy do zaksięgowania, nadal używana jest stara data zaksięgowania z poprzedniego okresu księgowania. Jednak ten okres został teraz zamknięty. W związku z tym pracownik działu zobowiązań (AP) musi ręcznie zmienić wszystkie daty księgowania na nowy okres księgowania dla wszystkich oczekujących faktur, które zostały wcześniej utworzone.

Funkcja opisana w tym artykule umożliwia skonfigurowanie systemu w taki sposób, aby automatycznie dostosowywał datę księgowania zgodnie z wymaganiami biznesowymi.

## <a name="parameter-for-automatically-adjusting-the-vendor-invoice-posting-date"></a>Parametr automatycznie korygujący datę księgowania faktury sprzedawcy

Wykonaj poniższe kroki, aby umożliwić systemowi automatyczną korektę daty księgowania dla faktur dostawców.

1.  Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia \> Parametry modułu rozrachunków z dostawcami**.
2.  Na karcie **Księga i podatek od sprzedaży** w polu **Automatycznie dostosuj datę księgowania** wybierz jedną z następujących wartości:

    - **Bez zmian** — system nie zmienia automatycznie daty księgowania podczas księgowania. Domyślnie ta opcja jest wybrana.
    - **Zawsze zmieniaj datę księgowania na datę systemową** — podczas księgowania system automatycznie zmienia datę księgowania na datę systemową.
    - **Zmień datę księgowania na datę systemową, gdy okres daty księgowania jest zamknięty lub wstrzymany** – System zmienia datę księgowania na datę systemową podczas księgowania, ale tylko wtedy, gdy okres odpowiadający dacie księgowania ma status **Zamknięty** lub **Zatrzymany**.
    - **Zmień datę księgowania na pierwszy dzień nowego okresu, gdy okres z datą księgowania jest zamknięty lub wstrzymany** – System zmienia datę księgowania na pierwszy dzień nowego okresu otwartego, ale tylko wtedy, gdy okres odpowiadający dacie księgowania ma status **Zamknięty** lub **Zatrzymany**.

> [!NOTE]
> Jeśli automatycznie skorygowana data księgowania znajduje się w nowym roku obrachunkowym, data księgowania faktury nie zostanie zaktualizowana. Użytkownik otrzyma błąd „Rok obrachunkowy został zmieniony. Sprawdź i wprowadź ponownie datę księgowania”. Aby można było zakturować, data księgowania faktury musi zostać zaktualizowana do daty nowego roku obrachunkowego.

## <a name="impact-of-posting-date-changes"></a>Wpływ zmiany daty księgowania

Gdy data księgowania na oczekującej fakturze sprzedawcy zostaje zmieniona, zmiana ta ma następujące skutki:

- **Data wykonania**

    - Jeśli pole **Data faktury** jest puste, termin płatności zostanie przeliczony na podstawie nowej daty księgowania i warunków płatności.
    - Jeśli pole **Data faktury** było wcześniej ustawione, zmiana daty księgowania nie wpływa na termin płatności.

- **Data rabatu**

    - Jeśli pole **Data faktury** jest puste, do obliczenia rabatu gotówkowego używana jest nowa data księgowania.
    - Jeśli pole **Data faktury** było wcześniej ustawione, rabat gotówkowy nie jest zmieniany.

- **Kurs waluty** – Data kursu waluty jest określana na podstawie ustawienia opcji **Uaktualnij księgowanie sprzedawcy za pomocą daty faktury** na zakładce **Faktura** strony **Parametry zobowiązań** (**Płatności \> Konfiguracja \> Parametry zobowiązań**).

    - Jeśli ta opcja ma wartość **Tak**, używana jest data faktury, a zmiana daty księgowania nie wpływa na kurs wymiany.
    - Jeśli dla tej opcji jest ustawiona wartość **Nie**, do obliczania kursu wymiany jest używana data księgowania. Gdy data księgowania jest aktualizowana, kwoty księgowe i sprawozdawcze są przeliczane na nowo. Dlatego należy ponownie przeprowadzić walidację dopasowania.

## <a name="validation"></a>Weryfikacja

Dwa inne pola w zakładce **Faktura** na stronie **Parametry zobowiązań** (**Parametry zobowiązań \> Konfiguracja \> Parametry zobowiązań**) mają wpływ na przetwarzanie faktur:

- Jeżeli pole **Sprawdź numer użytej faktury** jest ustawione na **Odrzucaj duplikaty w ramach roku podatkowego**, to podczas księgowania faktur system używa daty księgowania do sprawdzania duplikatów faktur.
- Jeśli pole **Wymagaj daty dokumentu na fakturze sprzedawcy** jest ustawione na **Opcja błędu**, wymagane jest pole **Data faktury w nagłówku faktury oczekującej**. Jeśli data faktury jest późniejsza niż data księgowania, system wyświetli komunikat o błędzie.
