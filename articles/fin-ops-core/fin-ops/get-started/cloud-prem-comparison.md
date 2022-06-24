---
title: Porównanie funkcji w chmurze i lokalnych
description: Ten artykuł przedstawia funkcje obsługiwane w chmurze i lokalnie.
author: sericks007
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 89563
ms.assetid: ''
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-11-29
ms.dyn365.ops.version: Platform update 9
ms.openlocfilehash: 4096089978032f150bf6d711711a948cf1d3232f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879783"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>Porównanie funkcji w chmurze i lokalnych

[!include [banner](../includes/banner.md)]

W tym artykule przedstawiono porównanie funkcji dostępnych w chmurze i w środowisku lokalnym dla następujących aplikacji:

- [Dynamics 365 Finance](cloud-prem-comparison.md#dynamics-365-finance)
- [Dynamics 365 Supply Chain Management](cloud-prem-comparison.md#dynamics-365-supply-chain-management)
- [Dynamics 365 Commerce](cloud-prem-comparison.md#dynamics-365-commerce)
- [Dynamics 365 Human Resources](cloud-prem-comparison.md#dynamics-365-human-resources)

Uwzględniliśmy również informacje dotyczące [funkcji programowania i administrowania](cloud-prem-comparison.md#development-and-administration-features).

W poniższej tabeli wymieniono zakresy aplikacji. Obsługa w chmurze i lokalnie jest wymieniona dla funkcji jako całości. W przypadku gdy określone funkcje różnią się od ogólnego obszaru, są wymienione w osobnym w wierszu w kolumnie funkcja.

## <a name="dynamics-365-finance"></a>Dynamics 365 Finance

| **Warstwowy**             | **Funkcja**                | **W chmurze** | **Lokalne** |
|---------------------|-----------------------------|-----------|-----------------|
| Zgodność i certyfikacje        |                                                                                           | Tak       | Tak             |
|                                      | Certyfikacja SOC 1 Typ 1                                                                | Tak       | Nie              |
| Integracja danych i zarządzanie nimi      |                                                                                           | Tak       | Tak             |
|                                      | Eksport danych do własnego magazynu danych                                                    | Tak       | Tak             |
|                                      | Włączenie eksportu aktualizacji przyrostowych do jednostki danych                                 | Tak       | Tak             |
|                                      | Integracje danych                                                                         | Tak       | Tak             |
| Zarządzanie dokumentami                  |                                                                                           | Tak       | Tak             |
| Zarządzanie finansami                 |                                                                                           | Tak       | Tak             |
| Pomoc                                 |                                                                                           | Tak       | Nie              |
| Zasoby ludzkie                      |                                                                                           | Tak       | Tak             |
| Analizy                         |                                                                                           | Tak       | Tak             |
|                                      | Raportowanie elektroniczne (ER)                                                                 | Tak       | Tak             |
|                                      | ER: Integracja z LCS                                                                  | Tak       | Nie              |
|                                      | ER: Integracja z SharePoint                                                           | Tak       | Nie              |
|                                      | ER: Integracja z Regulatory Configuration Services (RCS)                              | Tak       | Nie              |
|                                      | ER: używa lokalnego systemu plików jako magazynu na konfiguracje ER dostępne z repozytoriów ER | Nie        | Tak             |
|                                      | Integracja z PowerBI.com                                                              | Tak       | Nie              |
|                                      | Integracja z PowerBI Desktop                                                          | Nie        | Tak             |
|                                      | Analityczne obszary robocze                                                                     | Tak       | Nie              |
|                                      | Inteligentny proces biznesowy: zalecenia                                             | Tak       | Nie              |
|                                      | Tworzenie raportów dla usługi Power BI za pomocą interfejsu OData z wykorzystaniem aplikacji Power BI lub narzędzi PowerQuery dla programu Excel    | Tak       | Nie              |
|                                      | Usługi SQL Server Reporting Services (SSRS) obsługują skalowanie                                 | Tak       | Tak             |
|                                      | Dane telemetryczne są przesyłane do chmury                                                   | Tak       | Nie              |
| Usługi Lifecycle Services                   |                                                                                           | Tak       | Tak             |
|                                      | Konfigurowalne procesy biznesowe                                                           | Tak       | Nie              |
| Lokalizacje                        |                                                                                           | Tak       | Tak             |
| Aplikacja mobilna, obszary robocze i platforma |                                                                                           | Tak       | Tak             |
| Integracja z pakietem Office                   |                                                                                           | Tak       | Tak             |
| Administrowanie organizacją          |                                                                                           | Tak       | Tak             |
| Lista płac                              |                                                                                           | Tak       | Tak             |
|                                      | Przelew bezpośredni                                                                            | Tak       | Nie              |
| Zarządzanie projektami i ich księgowanie    |                                                                                           | Tak       | Tak             |
| Zabezpieczenia                             |                                                                                           | Tak       | Tak             |
| Zarządzanie usługą                   |                                                                                           | Tak       | Tak             |
| Klient sieci Web                           |                                                                                           | Tak       | Tak             |
|                                      | Rejestrator zadań — zapisywanie i ładowanie rejestracji zadań z biblioteki BPM                         | Tak       | Nie              |
| Pomoc techniczna                              |                                                                                           | Tak       | Tak             |
|                                      | Dostęp do pomocy technicznej w menu Pomoc i obsługa techniczna                                             | Tak       | Nie              |
|                                      | Zdarzenia biznesowe                                                                           | Tak       | Tak (łączność z Internetem jest wymagana albo niestandardowe punkty końcowe muszą zostać zaimplementowane w celu wysyłania/otrzymywania zdarzeń biznesowych w intranecie)              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **Warstwowy**                | **Funkcja**             | **W chmurze** | **Lokalne** |
|-------------------------|-------------------|-----------|-----------------|
| Zarządzanie składnikami majątku                     |                                                                                           | Tak       | Tak             |
| Zgodność i certyfikacje        |                                                                                           | Tak       | Tak             |
|                                      | Certyfikacja SOC 1 Typ 1                                                                | Tak       | Nie              |
| Rachunek kosztów                      |                                                                                           | Tak       | Tak             |
|                                      | Zestaw zawartości rachunku kosztów dla usługi Power BI                                                 | Tak       | Nie              |
|                                      | Obszar roboczy rachunku kosztów dla aplikacji mobilnej                                                  | Tak       | Nie              |
| Zarządzanie kosztami                      |                                                                                           | Tak       | Tak             |
|                                      | Pakiet zawartości modułu Zarządzanie kosztami w usłudze Power BI                                                 | Tak       | Nie              |
| Integracja danych i zarządzanie nimi      |                                                                                           | Tak       | Tak             |
|                                      | Rozszerzenie oparte na konfiguracji                                                            | Tak       | Nie              |
|                                      | Eksport danych do własnego magazynu danych                                                    | Tak       | Tak             |
|                                      | Włączenie eksportu aktualizacji przyrostowych do jednostki danych                                 | Tak       | Tak             |
|                                      | Integracje danych                                                                         | Tak       | Tak             |
| Zarządzanie dokumentami                  |                                                                                           | Tak       | Tak             |
| Pomoc                                 |                                                                                           | Tak       | Nie              |
| Analizy                         |                                                                                           | Tak       | Tak             |
|                                      | Raportowanie elektroniczne (ER)                                                                 | Tak       | Tak             |
|                                      | ER: Integracja z LCS                                                                  | Tak       | Nie              |
|                                      | ER: Integracja z SharePoint                                                           | Tak       | Nie              |
|                                      | ER: Integracja z Regulatory Configuration Services (RCS)                              | Tak       | Nie              |
|                                      | ER: używa lokalnego systemu plików jako magazynu na konfiguracje ER dostępne z repozytoriów ER | Nie        | Tak             |
|                                      | Integracja z PowerBI.com                                                              | Tak       | Nie              |
|                                      | Integracja z PowerBI Desktop                                                          | Nie        | Tak             |
|                                      | Analityczne obszary robocze                                                                     | Tak       | Nie              |
|                                      | Inteligentny proces biznesowy: zalecenia                                             | Tak       | Nie              |
|                                      | Tworzenie raportów dla usługi Power BI za pomocą interfejsu OData z wykorzystaniem aplikacji Power BI lub narzędzi PowerQuery dla programu Excel    | Tak       | Nie              |
|                                      | Usługi SQL Server Reporting Services (SSRS) obsługują skalowanie                                 | Tak       | Tak             |
|                                      | Dane telemetryczne są przesyłane do chmury                                                   | Tak       | Nie              |
| Zarządzanie zapasami                 |                                                                                           | Tak       | Tak             |
| Usługi Lifecycle Services                   |                                                                                           | Tak       | Tak             |
|                                      | Konfigurowalne procesy biznesowe                                                           | Tak       | Nie              |
| Lokalizacje                        |                                                                                           | Tak       | Tak             |
| Produkcja                        |                                                                                           | Tak       | Tak             |
| Planowanie główne i prognozy      |                                                                                           | Tak       | Tak             |
| Optymalizacja planowania                |                                                                                           | Tak       | Nie              |
| Aplikacja mobilna, obszary robocze i platforma |                                                                                           | Tak       | Tak             |
| Integracja z pakietem Office                   |                                                                                           | Tak       | Tak             |
| Administrowanie organizacją          |                                                                                           | Tak       | Tak             |
| Zaopatrzenie i sourcing             |                                                                                           | Tak       | Tak             |
|                                      | Korzystanie z katalogu zewnętrznego z zapotrzebowania na zakup                                   | Tak       | Nie              |
|                                      | Raporty Analiza wydatków i zakupów w usłudze Power BI                                                  | Tak       | Nie              |
| Zarządzanie informacjami o produktach       |                                                                                           | Tak       | Tak             |
| Dane produktu głównego                  |                                                                                           | Tak       | Tak             |
| Produkcja                           |                                                                                           | Tak       | Tak             |
|                                      | Raporty Wydajność produkcji w usłudze Power BI                                                   | Tak       | Nie              |
| Zarządzanie projektami i ich księgowanie    |                                                                                           | Tak       | Tak             |
| Sprzedaż                                |                                                                                           | Tak       | Tak             |
|                                      | Raporty Wyniki w zakresie sprzedaży i rentowności w usłudze Power BI                                      | Tak       | Nie              |
| Zabezpieczenia                             |                                                                                           | Tak       | Tak             |
| Zarządzanie serwisem                   |                                                                                           | Tak       | Tak             |
| Zarządzanie łańcuchem dostaw              |                                                                                           | Tak       | Tak             |
| Zarządzanie transportem            |                                                                                           | Tak       | Tak             |
| Współpraca z dostawcami                 |                                                                                           | Tak       | Nie              |
| Zarządzanie magazynem                 |                                                                                           | Tak       | Tak             |
|                                      | Mobilna aplikacja magazynu                                                                      | Tak       | Tak             |
|                                      | Raporty magazynowe w usłudze Power BI                                                              | Tak       | Nie              |
| Klient sieci Web                           |                                                                                           | Tak       | Tak             |
|                                      | Rejestrator zadań — zapisywanie i ładowanie rejestracji zadań z biblioteki BPM                         | Tak       | Nie              |
| Pomoc techniczna                              |                                                                                           | Tak       | Tak             |
|                                      | Dostęp do pomocy technicznej w menu Pomoc i obsługa techniczna                                             | Tak       | Nie              |

## <a name="dynamics-365-commerce"></a>Dynamics 365 Commerce 

Aby wyświetlić listę funkcji dostępnych we wdrożeniach lokalnych, zobacz [Funkcje Commerce dostępne we wdrożeniach lokalnych](../../../commerce/retail-onprem.md).

## <a name="dynamics-365-human-resources"></a>Dynamics 365 Human Resources 

| **Obszar**         | **Funkcja**         | **W chmurze** | **Lokalne** |
|------------------|---------------------|-----------|-----------------|
| Wszystkie obszary Zasobów ludzkich | Wszystkie funkcje Zasobów ludzkich | Tak       | Nie              |

## <a name="development-and-administration-features"></a>Funkcje programowania i administrowania

| **Obszar**                   | **Funkcja**                               | **W chmurze** | **Lokalne** |
|----------------------------|-------------------------------------------|-----------|-----------------|
| Kompilowanie i testowanie             |                                           | Tak       | Tak             |
| Możliwości rozszerzania              |                                           | Tak       | Tak             |
| Monitorowanie i telemetria   |                                           | Tak       | Tak             |
| Zgodność z platformą     |                                           | Tak       | Tak             |
| Obsługa                  |                                           | Tak       | Tak             |
|                            | Obsługiwanie środowisk                    | Tak       | Nie              |
| Analizator śledzenia               |                                           | Tak       | Tak             |
| PerfTimer                  |                                           | Tak       | Tak\*           |
| Uaktualnij                    |                                           | Tak       | Tak             |
|                            | Uaktualnij                                   | Tak       | Nie              |
|                            | Uaktualnienie i obsługa wcześniejszych wersji | Tak       | Nie              |
| Programowanie Visual Studio  |                                           | Tak       | Tak             |

\* W środowiskach lokalnych PerfTimer wyświetla tylko wyniki dla klienta.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
