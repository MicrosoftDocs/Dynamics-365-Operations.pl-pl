---
title: Używanie usługi fakturowania elektronicznego do importowania faktur od dostawców
description: Ten temat zawiera informacje dotyczące importowania faktur od dostawców przy użyciu usługi fakturowania elektronicznego.
author: gionoder
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 434bf1f6a5a727a71592493b85ab166cbeff2f0980c2c968c99973a03f4dc660
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751259"
---
# <a name="use-the-electronic-invoicing-service-to-import-vendor-invoices"></a>Używanie usługi fakturowania elektronicznego do importowania faktur od dostawców

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Ten temat zawiera informacje ułatwiające rozpoczęcie importowania faktur od dostawców przy użyciu usługi Elektroniczne fakturowanie. Prowadzi przez kolejne kroki konfiguracji w Regulatory Configuration Services (RCS), Dynamics 365 Finance i Dynamics 365 Supply Chain Management, których należy przestrzegać, aby otrzymywać elektroniczne faktury od sprzedawców.

## <a name="set-up-vendor-invoice-import-in-rcs"></a>Ustaw import faktury sprzedawcy w RCS
Aby skonfigurować importowanie faktury od dostawcy w pliku RCS, należy wykonać następujące czynności:

1. Zapoznaj się z listą [dostępnych funkcji fakturowania elektronicznego](e-invoicing-configuration-rcs.md#generally-available-features).
2. Wybierz i zaimportuj utworzoną funkcję fakturowania elektronicznego. Więcej informacji: [Importuj funkcję fakturowania elektronicznego od dostawcy konfiguracji firmy Microsoft](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider).
3. Utwórz funkcję fakturowania elektronicznego dla swojej organizacji. Więcej informacji: [Tworzenie funkcji fakturowania elektronicznego u dostawcy konfiguracji organizacji](e-invoicing-get-started.md#create-an-electronic-invoicing-feature-under-your-organization-provider).

## <a name="configure-an-email-account-channel"></a>Konfigurowanie kanału konta e-mail

Skonfiguruj kanał konta e-mail, jeśli utworzona funkcja fakturowania elektronicznego importuje elektroniczne faktury sprzedawców z załączonych plików otrzymywanych pocztą elektroniczną.

1. W RCS wybierz utworzoną funkcję fakturowania elektronicznego. Upewnij się, że wybierzesz wersję o stanie **Wersja robocza**.
2. Na karcie **Konfiguracja** w siatce wybierz konfigurację funkcji, a następnie wybierz pozycję **Edytuj**.
3. Na karcie **Kanał danych** w grupie pól **Parametry** wybierz **adres serwera** i wprowadź dostawcę konta e-mail.
4. Wybierz **Port serwera** i wprowadź port używany przez dostawcę konta e-mail.
5. Wybierz **Wpis tajny nazwy użytkownika** i wprowadź nazwę wpisu tajnego klucza, który zawiera identyfikator konta użytkownika poczty e-mail.
6. Wybierz **Wpis tajny hasła użytkownika** i wprowadź nazwę wpisu tajnego klucza, który zawiera identyfikator konta użytkownika poczty e-mail.
7. Wybierz **filtr tematu**. Przejrzyj i zaktualizuj ciąg znaków zawierający domyślny temat wiadomości e-mail, aby zidentyfikować wiadomość e-mail zawierającą elektroniczną fakturę sprzedawcy do zaimportowania.
8. W razie potrzeby na karcie **Reguły możliwości zastosowania** przejrzyj i zaktualizuj kryteria. Aby uzyskać więcej informacji, zobacz [Reguły możliwości zastosowania](e-invoicing-configuration-rcs.md#applicability-rules).
9. Wybierz przycisk **Zapisz** i zamknij stronę.

### <a name="configure-a-microsoft-sharepoint-channel"></a>Konfigurowanie kanału Microsoft SharePoint

Skonfiguruj kanał Microsoft SharePoint, jeśli funkcja fakturowania elektronicznego importuje elektroniczne faktury od dostawców z plików umieszczonych w folderach SharePoint.

1. W RCS wybierz utworzoną funkcję fakturowania elektronicznego. Upewnij się, że wybierzesz **wersję** o stanie **Wersja robocza**.
2. Na karcie **Konfiguracja** w siatce wybierz konfigurację Funkcji, a następnie wybierz pozycję **Edytuj**.
3. Na karcie **Kanał danych** w grupie pól **Parametry** wybierz **Adres SharePoint** i wprowadź URL SharePoint.
4. Wybierz **Port serwera** i wprowadź port używany przez dostawcę konta e-mail.
5. Wybierz **Identyfikator aplikacji** i wprowadź nazwę wpisu tajnego klucza, który zawiera identyfikator klienta SharePoint.
6. Wybierz **Wpis tajny aplikacji** i wprowadź nazwę wpisu tajnego klucza, który zawiera hasło klienta SharePoint.
7. Wybierz **Filtr pliku**. Przejrzyj i zaktualizuj maskę, aby odfiltrować pliki zawierające elektroniczną fakturę od dostawcy do zaimportowania.
8. W razie potrzeby na karcie **Reguły możliwości zastosowania** przejrzyj i zaktualizuj kryteria. Aby uzyskać więcej informacji, zobacz [Reguły możliwości zastosowania](e-invoicing-configuration-rcs.md#applicability-rules).
9. Wybierz przycisk **Zapisz** i zamknij stronę

### <a name="deploy-an-electronic-invoicing-feature"></a>Wdróż funkcję fakturowania elektronicznego

Aby wdrożyć funkcję fakturowania elektronicznego w środowisku usługi, zobacz temat [Wdrożenie funkcji elektronicznego fakturowania do środowiska serwisowego](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="set-up-vendor-invoice-import-in-finance-and-supply-chain-management"></a>Skonfiguruj import faktur dostawców w programie Finance i Supply Chain Management
Aby skonfigurować różne typy importowania faktur od dostawców, wykonaj kroki opisane w poniższych dwóch sekcjach.

### <a name="import-vendor-invoices-from-email"></a>Importowanie faktur od dostawców z wiadomości e-mail

1. Zaloguj się do środowiska Finance lub Supply Chain Management i sprawdź, czy jesteś we właściwej firmie.
2. Przejdź do **Administrowanie organizacją** > **Konfiguracja** > **Parametry dokumentu elektronicznego**.
3. Na karcie **Funkcje** upewnij się, że jest wybrana **Brazylijska faktura elektroniczna NF-e**.
4. Na karcie **Kanały zewnętrzne**, w grupie pól **Kanały** wybierz opcję **Dodaj**.
5. W polu **Kanał** wprowadź **NFe** (nazwę kanału podanego w konfiguracji kanału danych dla funkcji fakturowania elektronicznego w RCS).
6. W polu **Opis wprowadź** opis. W polu **Firma** wybierz firmę.
7. W polu **Kontekst dokumentu** wybierz opcję **Kontekst dokumentu skarbowego — kontekst dokumentu fiskalnego**.
8. W grupie pól **Importowanie źródeł** wybierz pozycję **Dodaj**.
9. W polu **Nazwa** wprowadź **XmlFile** (nazwę **Filtru załącznika** podanego w konfiguracji kanału danych dla funkcji fakturowania elektronicznego w RCS).
10. W polu **Opis** wprowadź opis, a w polu **Nazwa jednostki danych** wybierz pozycję **Odebrane dokumenty NF-e XML**.
11. W polu **Mapowanie modelu** wybierz pozycję **Import wiadomości e-mail NF-e, NF-e email import (BR)**, a następnie wybierz pozycję **Zapisz**.
12. Na karcie **Dokument elektroniczny** w grupie pól **Raportowanie elektroniczne** wybierz pozycję **Dodaj**, a w polu **Nazwa tabeli** wybierz pozycję **Odebrany dokument XML NF-e**.
13. W polu **Kontekst dokumentu** wybierz opcję **Kontekst zapytania o dokument skarbowy — kontekst dokumentu fiskalnego**.
14. W polu **Mapowanie modelu dokumentu elektronicznego** wybierz opcję **Mapowanie informacji — mapowanie dokumentu fiskalnego**.
15. Wybierz **Typy odpowiedzi**, a następnie wybierz opcję **Nowy**.
16. W polu **typu odpowiedzi** wprowadź **Odpowiedź**. W polu **Stan przesyłania** wpisz **Zaplanowane**.
17. W polu **Mapowanie modelu** wybierz opcję **Odwzorowanie modelu z komunikatu odpowiedzi - Format importu komunikatu odpowiedzi**.
18. Wybierz przycisk **Zapisz** i zamknij stronę.

### <a name="import-peppol-electronic-vendor-invoices"></a>Import elektronicznych faktur dostawców PEPPOL

1. W obszarze roboczym **Raportowanie elektroniczne** wybierz kafelek **Konfiguracje raportowania**.
2. Wybierz **Model kontekstowy faktury klienta** i utwórz konfigurację pochodną.
3. W **wersji roboczej** wybierz pozycję **Projektant**.
4. W drzewie **modeli danych** wybierz pozycję **Faktura dla odbiorcy**, a następnie wybierz opcję **Mapuj model na źródła danych**.
5. W drzewie **definicji** wybierz pozycję **CustomerInvoice**, a następnie wybierz pozycję **Projektant**.
6. W drzewku **Źródła danych** wybierz **Kontekst\_Kanał**. W polu **Wartość** wybierz **PEPPOL**. Jest to nazwa kanału podana w konfiguracji kanału danych dla funkcji Fakturowanie elektroniczne w RCS. 
7. Wybierz przycisk **Zapisz** i zamknij stronę.
8. Zamknij stronę.
9. Wybierz **model kontekstu faktury dla odbiorcy** i na skróconej karcie **Wersje** wybierz pozycję **Zmień stan** > **Zakończone**.
10. Przejdź do pola **Ustawienia administrowania organizacją** > **Ustawienia** > **Parametry dokumentu elektronicznego** i na karcie **Funkcje** upewnij się, że wybrano globalną fakturę elektroniczną **PEPPOL Globalne faktury elektroniczne**. 
11. Na karcie **Kanały zewnętrzne**, w grupie pól **Kanały** wybierz opcję **Dodaj**.
12. W polu **Kanał** wprowadź **PEPPOL**. W polu **Opis wprowadź** opis.
13. W polu **Firma** wybierz firmę. W polu **Kontekst dokumentu** wybierz opcję **Kontekst faktury dla klienta — kontekst dokumentu fiskalnego**.
14. Wybierz przycisk **Zapisz** i zamknij stronę.


## <a name="receive-electronic-invoices"></a>Odbieranie faktur elektronicznych
Aby otrzymać faktury elektroniczne, należy wykonać następujące czynności:

1. Przejdź do **Administrowanie organizacją** > **Okresowe** > **Dokumenty elektroniczne** > **Odbieraj dokumenty elektroniczne**.
2. Wybierz przycisk **OK** i zamknij stronę.

## <a name="view-receive-logs-for-electronic-invoices"></a>Wyświetlanie dzienników odbioru faktur elektronicznych

Aby wyświetlić dzienniki odbierania faktur elektronicznych, przejdź do **Zarządzanie organizacją** > **Okresowe** > **Dokumenty elektroniczne** > **Elektroniczny rejestr odbioru dokumentów**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
