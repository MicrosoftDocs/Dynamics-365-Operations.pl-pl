---
title: Ustaw Mapowanie pól stanu zamówienia sprzedaży
description: W tym temacie opisano sposób konfigurowania pól stanu zamówienia sprzedaży na potrzeby podwójnego zapisywania.
author: dasani-madipalli
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 5855581100606003c1faf6b88a0ab234ae378893
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4456193"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a>Ustaw Mapowanie pól stanu zamówienia sprzedaży

[!include [banner](../../includes/banner.md)]

Pola wskazujące stan zamówienia sprzedaży mają różne wartości wyliczenia w Microsoft Dynamics 365 Supply Chain Management i Dynamics 365 Sales. Dodatkowe ustawienia są wymagane do mapowania tych pól w trybie podwójnego zapisu.

## <a name="fields-in-supply-chain-management"></a>Pola w Supply Chain Management

W Supply Chain Management dwa pola odzwierciedlają stan zamówienia sprzedaży. Pola, które muszą być zmapowane, to **Stan** i **Stan dokumentu**.

Wyliczenie **Stan** określa ogólny stan zamówienia. Ten stan jest wyświetlany w nagłówku zamówienia.

Wyliczenie **Stan** oferuje następujące wartości:

- Otwarte zamówienie
- Dostarczone
- Zafakturowane
- Anulowane

Wyliczenie **Stanu dokumentu** określa najnowszy dokument, który został wygenerowany dla zamówienia. Jeśli na przykład zamówienie zostało potwierdzone, dokument jest potwierdzeniem zamówienia sprzedaży. Jeśli zamówienie sprzedaży jest częściowo zafakturowane, a pozostały wiersz zostanie potwierdzony, stan dokumentu pozostanie na **Fakturze**, ponieważ faktura jest generowana w późniejszym etapie procesu.

Wyliczenie **Stan dokumentu** oferuje następujące wartości:

- Potwierdzenie
- Lista pobrania
- Dokument dostawy
- Faktura VAT

## <a name="fields-in-sales"></a>Pola w Sales

W Sales dwa pola odzwierciedlają stan zamówienia sprzedaży. Pola, które muszą być zmapowane, to **Stan** i **Przetwarzanie dokumentu**.

Wyliczenie **Stan** określa ogólny stan zamówienia. Ma następujące wartości:

- Aktywni
- Przesłany
- Realizacja
- Zafakturowane
- Anulowane

Wyliczenie **Stanu przetwarzania** zostało wprowadzone w taki sposób, aby można było dokładniej zamapować stan z Supply Chain Management.

W poniższej tabeli przedstawiono mapowanie **Stanu przetwarzania** w Supply Chain Management.

| Stan przetwarzania   | Stan w Supply Chain Management | Stan dokumentu w Supply Chain Management |
|---------------------|-----------------------------------|--------------------------------------------|
| Aktywni              | Otwarte zamówienie                        | None                                       |
| Potwierdzone           | Otwarte zamówienie                        | Potwierdzenie                               |
| Pobrane              | Otwarte zamówienie                        | Lista pobrania                               |
| Częściowo dostarczone | Otwarte zamówienie                        | Dokument dostawy                               |
| Dostarczone           | Dostarczone                         | Dokument dostawy                               |
| Częściowo zafakturowane  | Dostarczone                         | Faktura VAT                                    |
| Zafakturowane            | Zafakturowane                          | Faktura VAT                                    |
| Anulowane           | Anulowane                         | Nie dotyczy                             |

W poniższej tabeli przedstawiono mapowanie **Stanu przetwarzania** między Sales a Supply Chain Management.

| Stan przetwarzania   | Stany w Sales | Stan w Supply Chain Management |
|---------------------|-----------------|-----------------------------------|
| Aktywni              | Aktywni          | Otwarte zamówienie                        |
| Potwierdzone           | Przesłany       | Otwarte zamówienie                        |
| Pobrane              | Przesłany       | Otwarte zamówienie                        |
| Częściowo dostarczone | Aktywni          | Otwarte zamówienie                        |
| Częściowo zafakturowane  | Aktywni          | Otwarte zamówienie                        |
| Częściowo zafakturowane  | Realizacja       | Dostarczone                         |
| Zafakturowane            | Zafakturowane        | Zafakturowane                          |
| Anulowane           | Anulowane       | Anulowane                         |

## <a name="setup"></a>Konfiguracja

Aby skonfigurować mapowanie dla pól stanu zamówienia sprzedaży, należy włączyć atrybuty **IsSOPIntegrationEnabled** i **isIntegrationUser**.

Aby włączyć atrybut **IsSOPIntegrationEnabled**, wykonaj następujące kroki.

1. W przeglądarce przejdź do strony `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`. Zastąp **\<test-name\>** łączem firmy w Sales.
2. Na otwartej stronie znajdź **organizationid** i zanotuj wartość.

    ![Znajdowanie organizationid](media/sales-map-orgid.png)

3. W Sales otwórz konsolę przeglądarki i uruchom następujący skrypt. Należy zastosować wartość **organizationid** z kroku 2.

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on record update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Kod JavaScript w konsoli przeglądarki](media/sales-map-script.png)

4. Upewnij się, że **IsSOPIntegrationEnabled** ma ustawioną wartość **true**. Użyj adresu URL z kroku 1, aby sprawdzić wartość.

    ![IsSOPIntegrationEnabled ma ustawioną wartość true](media/sales-map-integration-enabled.png)

Aby włączyć atrybut **isIntegrationUser**, wykonaj następujące kroki.

1. W Sales przejdź do **Ustawienia \> Dostosowania \> Dostosuj system**, wybierz pozycję **Jednostka użytkownika**, a następnie otwórz **Formularz \> Użytkownik**.

    ![Otwieranie formularza użytkownika](media/sales-map-user.png)

2. W Eksploratorze pól znajdź **Tryb użytkownika integracyjnego** i kliknij go dwukrotnie, aby dodać go do formularza. Zapisz zmiany.

    ![Dodanie pola tryb użytkownika integracyjnego do formularza](media/sales-map-field-explorer.png)

3. W module Sprzedaż należy posłużyć do **Ustawienia \> Zabezpieczenia \> Użytkownicy** i zmień widok z **Włączeni użytkownicy** na **Uzytkownicy aplikacji**.

    ![Zmienianie widoku z Włączonych użytkowników na Użytkowników aplikacji](media/sales-map-enabled-users.png)

4. Wybierz dwa wpisy dla **DualWrite IntegrationUser**.

    ![Lista użytkowników aplikacji](media/sales-map-user-mode.png)

5. Zmień wartość w polu **Tryb użytkownika integracyjnego** na **Tak**.

    ![Zmiana wartości pola Tryb użytkownika integracji](media/sales-map-user-mode-yes.png)

Twoje zamówienia sprzedaży są teraz zamapowane.
