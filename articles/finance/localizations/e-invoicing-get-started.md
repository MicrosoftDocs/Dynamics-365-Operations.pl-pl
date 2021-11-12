---
title: Rozpoczynanie pracy z fakturowaniem elektronicznym
description: Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z Faktury elektroniczne w rozwiązaniach Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 08/17/2021
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
ms.openlocfilehash: d0550228dc77ed255a0033bc3b0a4ec21d48a497
ms.sourcegitcommit: 2113678369f47944f8725ca656f461fa159f87f6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2021
ms.locfileid: "7700386"
---
# <a name="get-started-with-electronic-invoicing"></a>Rozpoczynanie pracy z fakturowaniem elektronicznym

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z Faktury elektroniczne. W tym temacie pokieruje użytkownika przez typowe kroki konfiguracji w usługach Regulatory Configuration Services (RCS) i Dynamics 365 Finance i wyjaśnimy kroki, które należy wykonać, aby przesłać dokumenty biznesowe i przejrzeć wyniki ich przetwarzania.

## <a name="prerequisites"></a>Wymagania wstępne

Przed wykonaniem procedur opisanych w tym temacie muszą być spełnione następujące wymagania wstępne:

- Skonfiguruj Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS) oraz środowisko Microsoft Dynamics 365 Finance lub Dynamics 365 Supply Chain Management. Aby uzyskać więcej informacji, zobacz temat [Wprowadzenie do administrowania usługą Fakturowanie elektroniczne](e-invoicing-get-started-service-administration.md).
- Utwórz dostawcę konfiguracji dla swojej organizacji. Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Importuj funkcję fakturowania elektronicznego od dostawcy konfiguracji firmy Microsoft 

1. Zaloguj się na konto usługi Regulatory Configuration Services (RCS).
2. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Faktury elektroniczne**.
3. Wybierz opcję **Import**, a następnie wybierz opcję **Synchronizuj**.
4. Filtruj kolumnę **Dostawca konfiguracji** według terminu **Microsoft**.
5. Wybierz nazwę funkcji fakturowania elektronicznego z tabeli, a następnie wybierz pozycję **Importuj**.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Utwórz funkcję fakturowania elektronicznego u swojego dostawcy organizacji

1. W RCS w obszarze **Funkcje** obszaru roboczego **Funkcje globalizacji**, wybierz kafelek **Faktury elektroniczne**.
2. Wybierz opcję **Dodaj** > **Na podstawie istniejącej funkcji**, a następnie w polu **Nazwa** wprowadź nazwę funkcji fakturowania elektronicznego.
3. W polu **Opis** wprowadź opis funkcji.
4. W **polu Funkcja podstawowa** wybierz zaimportowaną funkcję fakturowania elektronicznego od dostawcy konfiguracji firmy Microsoft.
5. Wybierz opcję **Utwórz funkcję**.

## <a name="country-specific-configuration-for-electronic-invoicing-feature"></a>Specyficzna dla kraju konfiguracja funkcji fakturowania elektronicznego

W zależności od kraju lub regionu funkcja Fakturowanie elektroniczne może wymagać konkretnej konfiguracji. 

Aby uzyskać szczegółowe informacje o tych krokach, zobacz dokumentację „Wprowadzenie” dla danego kraju lub regionu.

## <a name="import-the-model-mapping-configurations-from-electronic-reporting"></a>Importowanie konfiguracji mapowania modeli na potrzeby raportowania elektronicznego

1. W rcS wybierz obszar roboczy **Raportowanie elektroniczne**.
2. Wybierz dostawcę Konfiguracji **Microsoft**, a następnie **repozytoria**.
3. Wybierz opcję **Globalna** i w okienku akcji wybierz opcję **Otwórz**.
4. Zaimportuj konfiguracje mapowania modelu zgodnie z następującą tabelą według nazwy funkcji.

| Nazwa funkcji                         | Sesja mapowania konfiguracji modelu |
|--------------------------------------|-----------------------------|
| Faktury elektroniczne w Austrii (AT)    | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p> |
| Faktura elektroniczna w Belgii (BE)      | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p> |
| Brazylijski NF-e (BR)                  | <p>Model kontekstowy faktur sprzedaży</p><p>Dokumenty fiskalne</p><p>Model komunikatu odpowiedzi</p> |
| Brazylijski NFS-e ABRASF Curitiba (BR) | <p>Model kontekstowy faktur sprzedaży</p><p>Dokumenty fiskalne</p><p>Model komunikatu odpowiedzi</p> |
| Duńska faktura elektroniczna (DK)       | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p> |
| Egipska faktura elektroniczna (EG)     | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p><p>Model komunikatu odpowiedzi</p> |
| Estońska faktura elektroniczna (EE)     | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p> |
| Fińska faktura elektroniczna (FI)       | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p> |
| Francuska faktura elektroniczna (FR)       | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p> |
| Niemiecka faktura elektroniczna (DE)       | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p> |
| FatturaPA (IT)                       | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p> |
| Meksykańskie CFDI Interfactura (MX)       | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p><p>Model komunikatu odpowiedzi</p> |
| Holenderska faktura elektroniczna (NL)        | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p> |
| Norweska faktura elektroniczna (NIE)    | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p> |
| Hiszpańska faktura elektroniczna (ES)      | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p> |
| Faktura elektroniczna PEPPOL            | <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p> |
| Faktury elektroniczne dla Arabii Saudyjskiej (SA)| <p>Model kontekstowy faktur sprzedaży</p><p>Model faktury</p> |


## <a name="configure-the-application-setup"></a>Skonfiguruj ustawienia aplikacji

1. Wybierz utworzoną funkcję fakturowania elektronicznego.
2. Na karcie **Konfiguracje** wybierz opcję **Ustawienia aplikacji**.
3. W polu **Połącz aplikację** wybierz połączenie skojarzone z wystąpieniem zarządzaniem Finance lub Supply Chain Management.
4. W sekcji **Elektroniczne typy dokumentów** wybierz przycisk **Dodaj**.
5. Wybierz i wprowadź **wartość nazwy tabeli** zgodnie z następującą tabelą.

    | Nazwa funkcji                         | Dokument biznesowy | Nazwa tabeli |
    |--------------------------------------|-------------------|------------|
    | Faktury elektroniczne w Austrii (AT)    | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |
    | Faktura elektroniczna w Belgii (BE)      | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |
    | Brazylijski NF-e (BR)                  | <p>Dokument fiskalny</p><p>List korygujący</p> | Dokument fiskalny |
    | Brazylijski NFS-e ABRASF Curitiba (BR) | Obsługa dokumentów fiskalnych | Dokument fiskalny |
    | Duńska faktura elektroniczna (DK)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |
    | Egipska faktura elektroniczna (EG)     | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |
    | Estońska faktura elektroniczna (EE)     | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |
    | Fińska faktura elektroniczna (FI)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |
    | Francuska faktura elektroniczna (FR)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |
    | Niemiecka faktura elektroniczna (DE)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |
    | FatturaPA (IT)                       | <p>Faktura sprzedaży</p><p>Faktura projektu | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |
    | Meksykańskie CFDI Interfactura (MX)       | <p>Faktura sprzedaży</p><p>Dokument dostawy</p><p>Przeniesienie magazynowe</p><p>Dopełnienie płatności</p> | Arkusz faktur dla odbiorcy |
    | Holenderska faktura elektroniczna (NL)        | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |
    | Norweska faktura elektroniczna (NIE)    | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |
    | Hiszpańska faktura elektroniczna (ES)      | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |
    | Faktura elektroniczna PEPPOL            | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |
    | Faktury elektroniczne dla Arabii Saudyjskiej (SA)| <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Arkusz faktur dla odbiorcy</p><p>Faktura projektu</p> |

6. Dla każdej utworzonej nazwy tabeli wybierz i wprowadź wartość kontekstu zgodnie z poniższą tabelą.

    | Nazwa funkcji                         | Dokument biznesowy | Kontekst |
    |--------------------------------------|-------------------|---------|
    | Faktury elektroniczne w Austrii (AT)    | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |
    | Faktura elektroniczna w Belgii (BE)      | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |
    | Brazylijski NF-e (BR)                  | <p>Dokument fiskalny</p><p>List korygujący</p> | <p>Model kontekstu faktury dla odbiorcy — Kontekst dokumentu fiskalnego</p><p>Model kontekstu faktury dla odbiorcy — Kontekst listu korekcyjnego FD</p> |
    | Brazylijski NFS-e ABRASF Curitiba (BR) | Obsługa dokumentów fiskalnych| Model kontekstu faktury dla odbiorcy — Kontekst dokumentu fiskalnego |
    | Duńska faktura elektroniczna (DK)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |
    | Egipska faktura elektroniczna (EG)     | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |
    | Estońska faktura elektroniczna (EE)     | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |
    | Fińska faktura elektroniczna (FI)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |
    | Francuska faktura elektroniczna (FR)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |
    | Niemiecka faktura elektroniczna (DE)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |
    | FatturaPA (IT)                       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |
    | Meksykańskie CFDI Interfactura (MX)       | <p>Faktura sprzedaży</p><p>Dokument dostawy</p><p>Przeniesienie magazynowe</p><p>Dopełnienie płatności</p> | Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy |
    | Holenderska faktura elektroniczna (NL)        | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |
    | Norweska faktura elektroniczna (NIE)    | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |
    | Hiszpańska faktura elektroniczna (ES)      | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |
    | Faktura elektroniczna PEPPOL            | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |
    | Faktury elektroniczne dla Arabii Saudyjskiej (SA)| <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Model kontekstu faktury dla odbiorcy — kontekst faktury dla odbiorcy</p><p>Model kontekstu faktury dla odbiorcy — Kontekst faktury za projekt</p> |

7. Dla każdej nazwy tabeli i kontekstu wybierz i wprowadź wartość odwzorowania dokumentu biznesowego zgodnie z poniższą tabelą.

    | Nazwa funkcji                         | Dokument biznesowy | Mapowanie dokumentu biznesowego |
    |--------------------------------------|-------------------|---------------------------|
    | Faktury elektroniczne w Austrii (AT)    | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |
    | Faktura elektroniczna w Belgii (BE)      | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |
    | Brazylijski NF-e (BR)                  | <p>Dokument fiskalny</p><p>List korygujący</p> | <p>Mapowanie dokumentu fiskalnego – mapowanie dokumentu fiskalnego</p><p>Mapowanie dokumentu fiskalnego — mapowanie listu korygującego</p> |
    | Brazylijski NFS-e ABRASF Curitiba (BR) | Obsługa dokumentów fiskalnych | Mapowanie dokumentu fiskalnego – mapowanie dokumentu fiskalnego |
    | Duńska faktura elektroniczna (DK)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |
    | Egipska faktura elektroniczna (EG)     | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |
    | Estońska faktura elektroniczna (EE)     | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |
    | Fińska faktura elektroniczna (FI)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |
    | Francuska faktura elektroniczna (FR)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |
    | Niemiecka faktura elektroniczna (DE)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |
    | FatturaPA (IT)                       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |
    | Meksykańskie CFDI Interfactura (MX)       | <p>Faktura sprzedaży</p><p>Dokument dostawy</p><p>Przeniesienie magazynowe</p><p>Dopełnienie płatności</p> | Mapowanie modelu faktury — faktura dla odbiorcy |
    | Holenderska faktura elektroniczna (NL)        | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |
    | Norweska faktura elektroniczna (NIE)    | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |
    | Hiszpańska faktura elektroniczna (ES)      | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |
    | Faktura elektroniczna PEPPOL            | <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |
    | Faktury elektroniczne dla Arabii Saudyjskiej (SA)| <p>Faktura sprzedaży</p><p>Faktura projektu</p> | <p>Mapowanie modelu faktury — faktura dla odbiorcy</p><p>Mapowanie modelu faktury — Faktura za projekt</p> |


## <a name="country-specific-configuration-of-application-setup"></a>Specyficzna dla kraju konfiguracja aplikacji

W zależności od kraju lub regionu konfiguracja Aplikacji może wymagać konkretnej konfiguracji. 

Aby uzyskać szczegółowe informacje o tych krokach, zobacz dokumentację „Wprowadzenie” dla danego kraju lub regionu.

## <a name="deploy-the-electronic-invoicing-feature-to-service-environment"></a>Wdrażanie funkcji fakturowania elektronicznego w środowisku usługi

1. Na karcie **Wersje** wybierz wersję funkcji fakturowania elektronicznego, którą chcesz wdrożyć.
2. Wybierz **Zmień status** \> **Zakończone**.
3. Wybierz **Zmień status** \> **Opublikuj**.
4. Wybierz pozycję **Wdrażaj**.
5. Dla opcji **Wdrażanie połączonej aplikacji** ustaw wartość **Nie**.
6. Dla opcji **Wdróż w środowisku usługowym** ustaw wartość **Tak**.
7. W polu **Środowisko usługi** wybierz środowisko usługi fakturowania elektronicznego, w którym chcesz wdrożyć funkcję fakturowania elektronicznego.
8. W polu **Od dnia** wybierz datę, od kiedy funkcja fakturowania elektronicznego musi zostać w dostępna w Fakturowanie elektroniczne.
9. Kliknij przycisk **OK**.

## <a name="deploy-the-electronic-invoicing-feature-to-connected-application"></a>Wdrażanie funkcji fakturowania elektronicznego w Połączonej aplikacji

1. Na karcie **Wersje** wybierz wersję funkcji fakturowania elektronicznego, którą chcesz wdrożyć.
2. Wybierz pozycję **Wdrażaj**.
3. Dla opcji **Wdrażanie połączonej aplikacji** ustaw wartość **Tak**.
4. W polu **Połącz aplikację** wybierz połączenie skojarzone z wystąpieniem zarządzaniem Finance lub Supply Chain Management.
5. Dla opcji **Wdróż w środowisku usługowym** ustaw wartość **Nie**.
6. Kliknij przycisk **OK**.

## <a name="turn-on-the-electronic-invoicing-feature-in-finance-or-supply-chain-management"></a>Włącz funkcję Fakturowanie elektroniczne w Finance lub Supply Chain Management

1. Zaloguj się do Finance lub Supply Chain Management i sprawdź, czy jesteś we właściwej firmie.
2. Przejdź do **Administrowanie organizacją** \> **Konfiguracja** \> **Parametry dokumentu elektronicznego**.
3. Na karcie **Funkcje** wybierz funkcję specyficzną dla kraju/regionu, aby włączyć funkcję Fakturowanie elektroniczne w części Finance lub Supply Chain Management. W poniższej tabeli przedstawiono listę funkcji fakturowania elektronicznego dostępnych dla określonych krajów/regionów. 

    | Nazwa funkcji                                          | Kraj/region  |
    |-------------------------------------------------------|-----------------|
    | Faktury elektroniczne w Austrii (AT)                     | Austria         |
    | Faktura elektroniczna w Belgii (BE)                       | Belgia         |
    | Meksykański faktura elektroniczna CFDI (MX)                  | Meksyk          |
    | Duńska faktura elektroniczna (DK)                        | Dania         |
    | Holenderska faktura elektroniczna (NL)                         | Holandia |
    | Egipska faktura elektroniczna (EG)                      | Egipt           |
    | Estońska faktura elektroniczna (EE)                      | Estonia         |
    | Fińska faktura elektroniczna (FI)                       | Finlandia         |
    | Francuska faktura elektroniczna (FR)                        | Francja          |
    | Niemiecka faktura elektroniczna (DE)                        | Niemcy         |
    | Włoska faktura elektroniczna (IT)                       | Włochy           |
    | NF-e Federal — Brazylijska faktura elektroniczna (BR)      | Brazylia          |
    | NFS-e — faktura elektroniczna usługi brazylijskiej (miasto)   | Brazylia          |
    | Norweska faktura elektroniczna (NIE)                     | Norwegia          |
    | Faktura elektroniczna PEPPOL                             | Globalnie          |
    | Hiszpańska faktura elektroniczna (ES)                       | Hiszpania           |
    | Faktury elektroniczne dla Arabii Saudyjskiej (SA)                 | Arabia Saudyjska    |
    

4. Wybierz opcję **Zapisz**.

## <a name="issue-electronic-invoices"></a>Wystawiaj faktury elektroniczne

1. Przejdź do **Administrowanie organizacją** \> **Okresowe** \> **Dokumenty elektroniczne** \> **Prześlij dokumenty elektroniczne**.
2. W **Rekordy do uwzględnienia** na skróconej karcie, wybierz opcję **Filtr**.
3. Wybierz przycisk **Dodaj**, aby dodać nazwę tabeli do filtru kwerendy.
4. Wybierz tabelę zawierającą faktury.

    > [!NOTE]
    > Nazwa tabeli musi być wymieniona w tabeli w sekcji [Konfiguracja konfiguracji aplikacji wcześniej w tym temacie](#configure-the-application-setup).

5. Wybierz nazwę pola z tabeli, do której chcesz wysłać zapytanie.
6. Wprowadź nazwę tabeli i nazwę pola dla kryteriów zapytania.
7. Powtórz kroki od 5 do 6, aby dodać więcej pól i kryteriów do kwerendy, a następnie wybierz przycisk **OK**.
8. Kliknij przycisk **OK**.

## <a name="view-submission-logs"></a>Wyświetlanie dzienników przesyłania

1. Przejdź do **Administrowanie organizacją** \> **Okresowe** \> **Dokumenty elektroniczne** \> **Dziennik przysłania dokumentów elektronicznych**.
2. W polu **Typ dokumentu** wybierz tabelę zawierającą faktury.

    > [!NOTE]
    > Nazwa tabeli musi być wymieniona w tabeli w sekcji [Konfiguracja konfiguracji aplikacji wcześniej w tym temacie](#configure-the-application-setup).

3. Wybierz fakturę w siatce, a następnie wybierz opcję **Zapytanie** \> **Szczegóły przesłania**.


## <a name="related-topics"></a>Powiązane tematy

- [Omówienie fakturowania elektronicznego](e-invoicing-service-overview.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym — administrowanie usługami](e-invoicing-get-started-service-administration.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym dla Brazylii](e-invoicing-bra-get-started.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym dla Meksyku](e-invoicing-mex-get-started.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym dla Włoch](e-invoicing-ita-get-started.md)
- [Faktury elektroniczne odbiorcy w Egipcie](emea-egy-e-invoices.md)
- [Faktury elektroniczne dla odbiorcy w Arabii Saudyjskiej](emea-sau-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
