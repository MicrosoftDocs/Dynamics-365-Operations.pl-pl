---
title: Używanie usługi fakturowania elektronicznego do importowania faktur od dostawców
description: Ten temat zawiera informacje dotyczące importowania faktur od dostawców przy użyciu usługi fakturowania elektronicznego.
author: gionoder
ms.date: 09/03/2021
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
ms.openlocfilehash: c28adbfe532e77a52cab7625b9539d1e8e528bea
ms.sourcegitcommit: 81bc42551e6c9af6ad38908afb606ee1f8d3c44b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/03/2021
ms.locfileid: "7473383"
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
3. Na karcie **Kanał danych** w grupie pól **Parametry** w polu **Kanał danych** wprowadź nazwę kanału. Nazwa kanału nie może mieć więcej niż dziesięć znaków.
4. W polu **Adres serwera** wprowadź dostawcę konta e-mail. Na przykład adres serwera dla **https://outlook.live.com/** to **imap-mail.outlook.com**.
5. W polu **Port serwera** wprowadź port używany przez dostawcę konta e-mail. Na przykład port serwera dla **https://outlook.live.com/** to **993**.
6. W polu **Wpis tajny nazwy użytkownika** wprowadź nazwę wpisu tajnego klucza, który zawiera identyfikator konta użytkownika poczty e-mail. Ten klucz tajny musi zostać utworzony w usłudze Azure Key i skonfigurowany w środowisku usług. 
7. W polu **Wpis tajny hasła użytkownika** wprowadź nazwę wpisu tajnego klucza, który zawiera hasło konta użytkownika poczty e-mail.
8. Opcjonalnie — wprowadź wartości w polach **Z filtru**, **Filtr tematu** i **Filtr daty**.
9. Wprowadź nazw folderów skrzynki poczty, w których mają być wiadomości e-mail:

    - Zaimportowano z: **Folder główny**
    - Zapisane po pomyślnym przetworzeniu: **Folder archiwum**
    - Zapisane po nieudanym przetwarzaniu: **Folder błędów**, nie trzeba tworzyć tych folderów w skrzynce pocztowej. Foldery są tworzone automatycznie po pierwszym zaimportowaniu i przetworzeniu faktury elektronicznej. 
   
10. W grupie pól **Filtr załączników** dodaj informacje o filtrowaniu plików. Przetwarzane są tylko załączniki spełniające kryteria zdefiniowanego filtru. Na przykład można skonfigurować plik „\*.xml” dla załączników z rozszerzeniem XML. Nazwa załącznika jest używana w aplikacji Dynamics 365 Finance lub Dynamics 365 Supply Chain Management podczas konfiguracji. 
11. W razie potrzeby na karcie **Reguły możliwości zastosowania** przejrzyj i zaktualizuj kryteria. Pole **Kanał** musi mieć identyczną wartość jak podana wcześniej wartość **Kanał danych**. Aby uzyskać więcej informacji, zobacz [Reguły możliwości zastosowania](e-invoicing-configuration-rcs.md#applicability-rules).
12. Wybierz przycisk **Zapisz** i zamknij stronę.

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

## <a name="set-up-vendor-invoice-import-in-finance-or-supply-chain-management"></a>Skonfiguruj import faktur dostawców w aplikacji Finance lub Supply Chain Management
Aby skonfigurować różne typy importowania faktur od dostawców, wykonaj kroki opisane w poniższych dwóch sekcjach.

### <a name="import-brazilian-nf-e-from-email"></a>Import brazylijskiego NF-e z poczty e-mail

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
2. Wybierz opcję **Model kontekstu faktury dla odbiorcy**, a następnie wybierz pozycję **Utwórz konfigurację** > **Na podstawie nazwy: Model kontekstu faktury dla odbiorcy, Microsoft**, aby utworzyć konfigurację pochodną.
3. W obszarze wersji **próbnej** wybierz pozycję **Projektant**, a w drzewie **modelu danych** wybierz pozycję **Mapuj model na źródła danych**.
4. W drzewie **definicji** wybierz pozycję **DataChannel**, a następnie wybierz pozycję **Projektant**.
5. W drzewie **Źródła danych** rozwiń kontener **$Context\_Channel**. W polu **Wartość** wybierz pozycję **Edytuj** i wprowadź nazwę kanału danych. Jest to nazwa kanału podana w konfiguracji kanału danych dla funkcji Fakturowanie elektroniczne w RCS. 
7. Wybierz przycisk **Zapisz** i zamknij stronę.
8. Zamknij stronę.
9. Wybierz konfigurację pochodną utworzoną właśnie w **modelu kontekstu faktury dla odbiorcy**, a następnie na skróconej karcie **Wersje** wybierz pozycję **Zmień stan** > **Zakończone**.
10. Przejdź do pola **Ustawienia administrowania organizacją** > **Ustawienia** > **Parametry dokumentu elektronicznego** i na karcie **Funkcje** upewnij się, że wybrano globalną fakturę elektroniczną **PEPPOL Globalne faktury elektroniczne**. 
11. Na karcie **Kanały zewnętrzne**, w grupie pól **Kanały** wybierz opcję **Dodaj**.
12. W polu **Kanał** wprowadź nazwę kanału danych, a w polu **Opis** wprowadź opis.
13. W polu **Firma** wybierz firmę. 
14. W polu **Kontekst dokumentu** wybierz nową pochodną konfigurację z pola **modelu kontekstu faktury dla odbiorcy**. Opis mapowania powinien brzmieć **Kontekst kanału danych**.
15. W grupie pól **Importowanie źródeł** wybierz pozycję **Dodaj**.
16. W polu **Nazwa** wprowadź **nazwę filtru załączników**, a w polu **Nazwa encji danych** wybierz pozycję **Nagłówek faktury od dostawcy**.
17. W polu **Mapowanie modelu** wybierz pozycję **Import faktury od dostawcy — importuj fakturę od dostawcy**.
18. Kliknij przycisk **Zapisz** i zamknij stronę.


## <a name="receive-electronic-invoices"></a>Odbieranie faktur elektronicznych

Usługa fakturowania elektronicznego wykonuje dwa kroki podczas importowania faktur z kanałów danych:

1. Uzyskuje dostęp do skrzynki pocztowej i odczytywania wiadomości e-mail.
2. Przetwarza wiadomości e-mail. 
    
Aby wykonać te dwa kroki, klient powinien wywołać usługę ręcznie dla każdego kroku. Zaleca się jednak skonfigurowanie przetwarzania wsadowego w celu odbierania dokumentów elektronicznych.

Aby otrzymać faktury elektroniczne, należy wykonać następujące czynności:

1. Przejdź do **Administrowanie organizacją** > **Okresowe** > **Dokumenty elektroniczne** > **Odbieraj dokumenty elektroniczne**.
2. Wybierz przycisk **OK** i zamknij stronę.


## <a name="view-receive-logs-for-electronic-invoices"></a>Wyświetlanie dzienników odbioru faktur elektronicznych

Aby wyświetlić dzienniki odbierania faktur elektronicznych, przejdź do **Zarządzanie organizacją** > **Okresowe** > **Dokumenty elektroniczne** > **Elektroniczny rejestr odbioru dokumentów**.
Jeśli nie widać pomyślnie przetworzonych faktur, usuń filtr tabeli.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
