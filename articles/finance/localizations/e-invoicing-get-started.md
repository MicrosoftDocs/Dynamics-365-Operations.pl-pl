---
title: Rozpocznij pracę z dodatkiem Faktury elektroniczne
description: Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne w rozwiązaniach Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 56227e031f8205836bcae9ce26006fc8091c2863
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592557"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Rozpocznij pracę z dodatkiem Faktury elektroniczne

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z dodatkiem Faktury elektroniczne.

W poniższej tabeli wymieniono funkcje fakturowania elektronicznego oraz dokumenty biznesowe, których można używać.

| Nazwa funkcji                         | Dokument biznesowy |
|--------------------------------------|-------------------|
| Faktury elektroniczne w Austrii (AT)    | <p>Faktura sprzedaży</p><p>Faktura projektu</p> |
| Faktura elektroniczna w Belgii (BE)      | <p>Faktura sprzedaży</p><p>Faktura projektu</p> |
| Brazylijski NF-e (BR)                  | <p>Dokument fiskalny modelu 55</p><p>List korygujący</p> |
| Brazylijski NFS-e ABRASF Curitiba (BR) | Obsługa dokumentów fiskalnych |
| Duńska faktura elektroniczna (DK)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> |
| Egipska faktura elektroniczna (EG)     | <p>Faktura sprzedaży</p><p>Faktura projektu</p> |
| Estońska faktura elektroniczna (EE)     | <p>Faktura sprzedaży</p><p>Faktura projektu</p> |
| Fińska faktura elektroniczna (FI)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> |
| Francuska faktura elektroniczna (FR)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> |
| Niemiecka faktura elektroniczna (DE)       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> |
| FatturaPA (IT)                       | <p>Faktura sprzedaży</p><p>Faktura projektu</p> |
| Meksykańskie CFDI Interfactura (MX)       | <p>Faktura sprzedaży</p><p>Dokument dostawy</p><p>Przeniesienie magazynowe</p><p>Dopełnienie płatności</p> |
| Holenderska faktura elektroniczna (NL)        | <p>Faktura sprzedaży</p><p>Faktura projektu</p> |
| Norweska faktura elektroniczna (NIE)    | <p>Faktura sprzedaży</p><p>Faktura projektu</p> |
| Hiszpańska faktura elektroniczna (ES)      | <p>Faktura sprzedaży</p><p>Faktura projektu</p> |
| Faktura elektroniczna PEPPOL            | <p>Faktura sprzedaży</p><p>Faktura projektu</p> |

## <a name="prerequisites"></a>Wymagania wstępne

Przed wykonaniem procedur opisanych w tym temacie muszą być spełnione następujące wymagania wstępne:

- Skonfiguruj usługę Regulatory Configuration Services (RCS) i środowisko Microsoft Dynamics 365 Finance lub Dynamics 365 Supply Chain Management, tak aby można było przesłać do dodatku Fakturowanie elektroniczne.
- Utwórz środowisko usługi i opublikuj je w dodatku Fakturowanie elektroniczne. Aby uzyskać więcej informacji, zobacz temat [Wprowadzenie do administrowania usługą dodatku Fakturowanie elektroniczne](e-invoicing-get-started-service-administration.md).
- Utwórz połączoną aplikację. Aby uzyskać więcej informacji, zobacz temat [Wprowadzenie do administrowania usługą dodatku Fakturowanie elektroniczne](e-invoicing-get-started-service-administration.md).
- Utwórz dostawcę konfiguracji dla swojej organizacji. Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Importuj funkcję fakturowania elektronicznego od dostawcy konfiguracji firmy Microsoft 

1. Zaloguj się na konto usługi Regulatory Configuration Services (RCS).
2. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Dodatek Faktury elektroniczne**.
3. Wybierz opcję **Import**, a następnie wybierz opcję **Synchronizuj**.
4. Filtruj kolumnę **Dostawca konfiguracji** według terminu **Microsoft**.
5. Wybierz nazwę funkcji fakturowania elektronicznego z tabeli na początku tego tematu, a następnie wybierz pozycję **Importuj**.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Utwórz funkcję fakturowania elektronicznego u swojego dostawcy organizacji

1. W RCS w sekcji **Funkcje** obszaru roboczego **funkcji Globalizacja** wybierz kafelek **dodatku Fakturowanie elektroniczne**.
2. Wybierz opcję **Dodaj** > **Na podstawie istniejącej funkcji**, a następnie w polu **Nazwa** wprowadź nazwę funkcji fakturowania elektronicznego.
3. W polu **Opis** wprowadź opis funkcji.
4. W **polu Funkcja podstawowa** wybierz zaimportowaną funkcję fakturowania elektronicznego od dostawcy konfiguracji firmy Microsoft.
5. Wybierz opcję **Utwórz funkcję**.

## <a name="configure-the-electronic-invoicing-feature"></a>Skonfiguruj funkcję fakturowania elektronicznego

W zależności od kraju lub regionu funkcja Fakturowanie elektroniczne może wymagać dodatkowej konfiguracji. 

Aby uzyskać szczegółowe informacje o tych krokach, zobacz dokumentację „Wprowadzenie” dla danego kraju lub regionu.

## <a name="configure-the-application-setup"></a>Skonfiguruj ustawienia aplikacji

1. Wybierz utworzoną funkcję fakturowania elektronicznego.
2. Na karcie **Wersja** sprawdź, czy jest wybrana **Wersja robocza**.
3. Na karcie **Konfiguracje** wybierz opcję **Ustawienia aplikacji**.

    > [!NOTE]
    > Sprawdź, czy Twoja organizacja jest ustawiona jako **Aktywny** dostawca konfiguracji. Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych.](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

4. Wybierz opcję **Konfiguracja funkcji**, a następnie wybierz pozycję **Połączona aplikacja**.
5. W sekcji **Elektroniczne typy dokumentów** wybierz przycisk **Dodaj**.
6. W przypadku każdego dokumentu biznesowego, który obsługuje funkcja, wybierz i wprowadź wartość w **Nazwie tabeli** zgodnie z następującą tabelą.

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

7. W przypadku każdego dokumentu biznesowego, który obsługuje funkcja, wybierz i wprowadź wartość w **Kontekst** zgodnie z następującą tabelą.

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

8. W przypadku każdego dokumentu biznesowego, który obsługuje funkcja, wybierz i wprowadź wartość w **Mapowanie dokumentów biznesowych** zgodnie z następującą tabelą.

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

W zależności od kraju lub regionu funkcja Fakturowanie elektroniczne może wymagać dodatkowej konfiguracji.

Aby uzyskać szczegółowe informacje o tych krokach, zobacz dokumentację „Wprowadzenie” dla danego kraju lub regionu.

## <a name="deploy-the-electronic-invoicing-feature"></a>Wdróż funkcję fakturowania elektronicznego

1. Na karcie **Wersje** wybierz wersję funkcji fakturowania elektronicznego, którą chcesz wdrożyć.
2. Wybierz **Zmień status** \> **Zakończone**.
3. Wybierz **Zmień status** \> **Opublikuj**.
4. Wybierz pozycję **Wdrażaj**.
5. Dla opcji **Wdrażanie połączonej aplikacji** ustaw wartość **Tak**.
6. Na stronie **Połącz aplikację** wybierz połączenie skojarzone z wystąpieniem zarządzaniem Finance lub Supply Chain Management.
7. Dla opcji **Wdróż w środowisku usługowym** ustaw wartość **Tak**.
8. W polu **Środowisko usługi** wybierz środowisko usługi dodatkowe fakturowania elektronicznego, w którym chcesz wdrożyć funkcję fakturowania elektronicznego.
9. W polu **Od dnia** wybierz datę, od kiedy funkcja fakturowania elektronicznego musi zostać w dostępna w dodatku Fakturowanie elektroniczne.
10. Kliknij przycisk **OK**.

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
    | Faktura elektroniczna PEPPOL                             | Globalna          |
    | Hiszpańska faktura elektroniczna (ES)                       | Hiszpania           |

4. Wybierz opcję **Zapisz**.

## <a name="issue-electronic-invoices"></a>Wystawiaj faktury elektroniczne

1. Przejdź do **Administrowanie organizacją** \> **Okresowe** \> **Dokumenty elektroniczne** \> **Prześlij dokumenty elektroniczne**.
2. Na skróconej karcie **Rekord do uwzględnienia** wybierz opcję **Filtr**.
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

- [Omówienie dodatku do fakturowania elektronicznego](e-invoicing-service-overview.md)
- [Rozpoczynanie pracy z dodatkiem do fakturowania elektronicznego — administrowanie usługami](e-invoicing-get-started-service-administration.md)
- [Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Brazylii](e-invoicing-bra-get-started.md)
- [Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Meksyku](e-invoicing-mex-get-started.md)
- [Rozpocznij pracę z dodatkiem Faktury elektroniczne dla Włoch](e-invoicing-ita-get-started.md)
- [Faktury elektroniczne odbiorcy w Egipcie](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
