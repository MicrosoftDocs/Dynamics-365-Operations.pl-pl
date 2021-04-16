---
title: Konfigurowanie i przetwarzania faktur cyklicznych
description: W tym artykule wyjaśniono, jak konfigurować i przetwarzać faktury cykliczne. Faktur cyklicznych można używać, jeśli regularnie trzeba fakturować odbiorców na tę samą kwotę.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76dd6b21207b61dfb96e4d9538b5e6ffc1c6b02d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835132"
---
# <a name="set-up-and-process-recurring-invoices"></a>Konfigurowanie i przetwarzania faktur cyklicznych

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak konfigurować i przetwarzać faktury cykliczne. Faktur cyklicznych można używać, jeśli regularnie trzeba fakturować odbiorców na tę samą kwotę.

<a name="create-a-recurring-free-text-invoice-template"></a>Tworzenie szablonu cyklicznej faktury niezależnej
---------------------------------------------

Aby wystawiać faktury dla odbiorców za te same usługi w regularnych odstępach czasu, trzeba zdefiniować szablon faktury niezależnej, który może być używany wielokrotnie do tworzenia faktur. Szablon zawiera następujące informacje:

-   Informacje nagłówka, takie jak grupy podatków, warunki płatności i metody płatności
-   Informacje wiersza, takie jak opis usługi, konta przychodów, cena jednostkowa i kwota faktury
-   Opłaty za wysyłkę lub obsługę
-   Zasady podziału księgowań łącznie z informacjami o wymiarach finansowych, takie jak centra kosztów i jednostki biznesowe

W efekcie tworzysz całą fakturę i zapisujesz ją jako szablon. Szablony konfiguruje się za pomocą strony **Faktury cykliczne**.

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a>Przypisywanie szablonu faktury niezależnej do odbiorcy i wpisywanie szczegółów cyklu
Po utworzeniu szablonu trzeba przypisać szablon do odbiorców, którym chcesz wystawić fakturę. Oprócz tego trzeba określić, kiedy i jak często faktura ma być używana. Szablony można przypisywać na karcie **Faktura** na stronie **Odbiorcy**. Dodaj szablon do listy i zaktualizuj następujące informacje:

-   Data rozpoczęcia i, opcjonalnie, data zakończenia cyklu fakturowania
-   Częstotliwość cyklu fakturowania (na przykład codziennie lub raz na miesiąc)
-   Maksymalna kwota fakturowania (jeśli ta informacja jest wymagana)

Odbiorca może mieć wiele szablonów z różnymi częstotliwościami.

## <a name="generate-the-recurring-invoices"></a>Generowane faktur cyklicznych
Na stronie **Faktury cykliczne** jest zadanie do przetwarzania szablonów faktur cyklicznych. Określasz datę faktury i szablon do generowania faktur. Faktury będą generowane i przypisywane do jednego cyklicznego identyfikatora dla każdej przetwarzanej grupy faktur.

<a name="post-recurring-free-text-invoices"></a>Księgowanie cyklicznych faktur niezależnych
---------------------------------

Po wygenerowaniu faktur cyklicznych w zadaniu księgowania w zadaniu pojawiają się identyfikatory cyklu faktur na stronie **Faktury cykliczne**. Można wyświetlić wszystkie faktury dla identyfikatora cyklu, klikając łącze. Podczas przeglądu faktur dla identyfikatora cyklu można usunąć indywidualne faktury. Ustawienia cyklu odbiorcy zostaną zresetowane dla tego szablonu, tak aby można było go wygenerować ponownie później. Można księgować jedną, wiele lub wszystkie faktury dla identyfikatora cyklu. Jeśli przepływy pracy są włączone, należy kliknąć opcję **Prześlij** przed zaksięgowaniem faktury.

<a name="print-recurring-free-text-invoices"></a>Drukowanie cyklicznych faktur niezależnych
----------------------------------

Po zaksięgowaniu faktur cyklicznych można je drukować ze strony listy faktur niezależnych. Można drukować faktury, które są wybrane, lub można wybrać zakres faktur do wydrukowania.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]