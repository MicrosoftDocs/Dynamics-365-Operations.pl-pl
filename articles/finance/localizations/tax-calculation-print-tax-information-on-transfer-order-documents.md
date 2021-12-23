---
title: Drukowanie informacji podatkowych na dokumentach polecenia przelewu
description: W tym temacie wyjaśniono, w jaki sposób informacje podatkowe określane przez usługę obliczania podatku mogą być drukowane na dokumentach polecenia przelewu.
author: Kai-Cloud
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-10-12
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 174cbd85139db5cee75481041fb721dc7646ab66
ms.sourcegitcommit: eef5d9935ccd1e20e69a1d5b773956aeba4a46bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2021
ms.locfileid: "7913609"
---
# <a name="print-tax-information-on-transfer-order-documents"></a>Drukowanie informacji podatkowych na dokumentach polecenia przelewu

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób drukowania informacji podatkowych na dokumentach polecenia przelewu. Możesz wydrukować dokument faktury pro-forma polecenia przelewu dla przesunięć magazynowych, które są uznawane za wewnątrzwspólnotową dostawę i wewnątrzwspólnotowe nabycie zgodnie z przepisami Unii Europejskiej (UE) dotyczącymi podatku od wartości dodanej (VAT). 

Do dokumentów polecenia przelewu dodawane są następujące dane istotne z podatkowego punktu widzenia:

- Nazwy oraz adresy „od” i „do” w przypadku transferu akcji
- Numery identyfikacji podatkowej dostawcy i odbiorcy
- Cena jednostkowa i podstawa opodatkowania dostarczonych towarów
- Kodeks podatkowy, stawka podatkowa, kwota podatku i dyrektywy podatkowe

Aby skonfigurować te dane, należy wykonać następujące główne kroki.

1. [Włącz i skonfiguruj funkcję podatkową dla poleceń przelewu](tasks/Tax-feature-support-for-transfer-order.md).
2. [Tworzenie i konfigurowanie wielu numerów rejestracji podatkowej dla osoby prawnej](emea-multiple-vat-registration-numbers.md).
3. Ustaw kod zwolnienia, opis, dyrektywy podatkowe i kod wydruku w kodach podatkowych. W tym przykładzie tworzone i zsynchronizowane w Microsoft Dynamics 365 Finance są trzy kody podatków: **NL-Exempt**, **BE-RC-21** oraz **BE-RC+21**.

    1. W module Finance wybierz opcje **Podatek** \> **Konfiguracja** \> **Podatek od sprzedaży** \> **Kody zwolnione z podatku od sprzedaży**.
    2. Wybierz **Edytuj**, a następnie wprowadź opis dla kodu zwolnienia **EC**. Na przykład wpisz **Wysyłki EC zwolnione z podatku z numerem rejestracji podatkowej**.
    3. Wybierz kolejno opcje **Podatek** \> **Podatki pośrednie** \> **Podatek** \> **Kody podatków**.
    4. Wybierz kod podatku **BE-RC-21**, a następnie **dyrektywy podatkowe**.
    5. Wybierz pozycję **Nowy**.
    6. W polu **Język** wybierz **EN-US**. Następnie w polu **Tekst** należy wpisać **Dokument określający przeniesienie towarów w rozumieniu art. 138. 2 lit. c) dyrektywy 2006/112/WE**.
    7. Zamknij stronę.
    8. Na skróconej karcie **Ogólne**, w polu **Drukuj** wybierz **Stawkę podatku od sprzedaży**.
    8. Wybierz kod podatku **NL-Exempt**, a następnie na skróconej karcie **Ogólne** w polu **Drukuj** wybierz **Stawkę podatku od sprzedaży**.

    > [!NOTE] 
    > Kod podatkowy, stawka podatkowa oraz opis zwolnienia z podatku nie są drukowane na dokumentach polecenia przelewu, jeśli nie zachowano opisu kodu zwolnienia lub dyrektyw podatkowych dla kodu podatkowego.

## <a name="print-the-transfer-order---shipment-document"></a>Wydrukuj polecenie przelewu — dokument wysyłkowy

Po wysłaniu przelewu należy wykonać poniższe czynności w celu wydrukowania dokumentu zlecenia przelewu — wysyłki.

1. Przejdź do **Zarządzanie zapasami** \> **Zapytania i raporty** \> **Zlecenia przelewu** \> **Wysyłka**.
2. Na zakładce **Parametry**, w grupie **Drukuj**, włącz **Informacje podatkowe**.
3. Na karcie **Rekordy do uwzględnienia** wybierz opcję **Filtruj**, wybierz numer zamówienia przeniesienia, a następnie wybierz przycisk **OK**.
4. Wybierz **OK**, aby wydrukować polecenie przelewu – dokument wysyłki.

## <a name="print-the-transfer-order---receipt-document"></a>Wydrukuj polecenie przelewu — dokument odbioru

Po otrzymaniu przelewu należy wykonać poniższe czynności w celu wydrukowania dokumentu polecenia przelewu - pokwitowania.

1. Przejdź do **Zarządzanie zapasami** \> **Zapytania i raporty** \> **Zlecenia przelewu** \> **Odbiór**.
2. Na zakładce **Parametry**, w grupie **Drukuj**, włącz **Informacje podatkowe**.
3. Na karcie **Rekordy do uwzględnienia** wybierz opcję **Filtruj**, wybierz numer zamówienia przeniesienia, a następnie wybierz przycisk **OK**.
4. Wybierz **OK**, aby wydrukować polecenie przelewu – dokument odbioru.

## <a name="print-the-transfer-overview-document"></a>Drukowanie dokumentu przeglądu przelewów

Wykonaj poniższe kroki, aby wydrukować dokument przeglądu przelewów.

> [!NOTE]
> Informacja podatkowa jest dostępna tylko wtedy, gdy polecenie przelewu zostało wysłane lub otrzymane.

1. Przejdź do **Zarządzanie zapasami** \> **Zapytania i raporty** \> **Zlecenia przelewu** \> **Przegląd transferów**.
2. Na zakładce **Parametry**, w grupie **Drukuj**, włącz **Informacje podatkowe**.
3. Na karcie **Rekordy do uwzględnienia** wybierz opcję **Filtruj**, wybierz numer zamówienia przeniesienia, a następnie wybierz przycisk **OK**.
4. Wybierz **OK**, aby wydrukować dokument przeglądu przelewów.

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
