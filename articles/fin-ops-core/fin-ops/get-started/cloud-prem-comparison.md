---
title: Porównanie funkcji w chmurze i lokalnych
description: Ten temat przedstawia funkcje obsługiwane w chmurze i lokalnie.
author: sericks007
manager: AnnBe
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 89563
ms.assetid: ''
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-11-29
ms.dyn365.ops.version: Platform update 9
ms.openlocfilehash: 309131f0d7390288a46f84b1375bd87922407159
ms.sourcegitcommit: a017fc0583a894382b959e22511231dd07d4254a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/14/2021
ms.locfileid: "4959901"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>Porównanie funkcji w chmurze i lokalnych

[!include [banner](../includes/banner.md)]

W tym temacie przedstawiono porównanie funkcji dostępnych w chmurze i w środowisku lokalnym dla następujących aplikacji:

- [Dynamics 365 Finance](cloud-prem-comparison.md#dynamics-365-finance)
- [Dynamics 365 Supply Chain Management](cloud-prem-comparison.md#dynamics-365-supply-chain-management)
- [Dynamics 365 Commerce](cloud-prem-comparison.md#dynamics-365-commerce)
- [Dynamics 365 Human Resources](cloud-prem-comparison.md#dynamics-365-human-resources)

Uwzględniliśmy również informacje dotyczące [funkcji programowania i administrowania](cloud-prem-comparison.md#development-and-administration-features).

W poniższej tabeli wymieniono zakresy aplikacji. Obsługa w chmurze i lokalnie jest wymieniona dla funkcji jako całości. W przypadku gdy określone funkcje różnią się od ogólnego obszaru, są wymienione w osobnym w wierszu w kolumnie funkcja.

## <a name="dynamics-365-finance"></a>Rozwiązanie Dynamics 365 Finance

| **Obszar**             | **Funkcja**                | **W chmurze** | **Lokalne** |
|---------------------|-----------------------------|-----------|-----------------|
| Zgodność i certyfikacje        |                                                                                           | Tak       | Tak             |
|                                      | Certyfikacja SOC 1 Typ 1                                                                | Tak       | Nie              |
| Integracja danych i zarządzanie nimi      |                                                                                           | Tak       | Tak             
|                                      | Eksport danych do własnego magazynu danych                                                    | Tak       | Tak             |
|                                      | Włączenie eksportu aktualizacji przyrostowych do jednostki danych                                 | Tak       | Tak              |
|                                      | Integracje danych                                                                         | Tak       | Tak             |
| Zarządzanie dokumentami                  |                                                                                           | Tak       | Tak             |
| Zarządzanie finansami                 |                                                                                           | Tak       | Tak             |
| Pomoc                                 |                                                                                           | Tak       | Nr              |
| Zasoby ludzkie                      |                                                                                           | Tak       | Tak             |
| Analizy                         |                                                                                           | Tak       | Tak             |
|                                      | Raportowanie elektroniczne (ER)                                                                 | Tak       | Tak             |
|                                      | ER: Integracja z LCS                                                                  | Tak       | Nie              |
|                                      | ER: Integracja z SharePoint                                                           | Tak       | Nie              |
|                                      | ER: Integracja z Regulatory Configuration Services (RCS)                              | Tak       | Nie              |
|                                      | ER: używa lokalnego systemu plików jako magazynu na konfiguracje ER dostępne z repozytoriów ER | Nr        | Tak             |
|                                      | Integracja z PowerBI.com                                                              | Tak       | Nr              |
|                                      | Integracja z PowerBI Desktop                                                          | Nr        | Tak             |
|                                      | Analityczne obszary robocze                                                                     | Tak       | Nr              |
|                                      | Inteligentny proces biznesowy: zalecenia                                             | Tak       | Nr              |
|                                      | Tworzenie raportów dla usługi Power BI za pomocą interfejsu OData z wykorzystaniem aplikacji Power BI lub narzędzi PowerQuery dla programu Excel    | Tak       | Nr              |
|                                      | Usługi SQL Server Reporting Services (SSRS) obsługują skalowanie                                 | Tak       | Nie              |
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
|                                      | Rejestrator zadań — zapisywanie i ładowanie rejestracji zadań z biblioteki BPM                         | Tak       | Nr              |
| Pomoc techniczna                              |                                                                                           | Tak       | Tak             |
|                                      | Dostęp do pomocy technicznej w menu Pomoc i obsługa techniczna                                             | Tak       | Nie              |
|                                      | Zdarzenia biznesowe                                                                           | Tak       | Tak (łączność z Internetem jest wymagana albo niestandardowe punkty końcowe muszą zostać zaimplementowane w celu wysyłania/otrzymywania zdarzeń biznesowych w intranecie)              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **Warstwowy**                | **Funkcja**             | **W chmurze** | **Lokalne** |
|-------------------------|-------------------|-----------|-----------------|
| Zarządzanie składnikami majątku                     |                                                                                           | Tak       | Nr |
| Zgodność i certyfikacje        |                                                                                           | Tak       | Tak             |
|                                      | Certyfikacja SOC 1 Typ 1                                                                | Tak       | Nr              |
| Rachunek kosztów                      |                                                                                           | Tak       | Tak             |
|                                      | Zestaw zawartości rachunku kosztów dla usługi Power BI                                                 | Tak       | Nr              |
|                                      | Obszar roboczy rachunku kosztów dla aplikacji mobilnej                                                  | Tak       | Nr              |
| Zarządzanie kosztami                      |                                                                                           | Tak       | Tak             |
|                                      | Pakiet zawartości modułu Zarządzanie kosztami w usłudze Power BI                                                 | Tak       | Nr              |
| Integracja danych i zarządzanie nimi      |                                                                                           | Tak       | Tak             |
|                                      | Rozszerzenie oparte na konfiguracji                                                            | Tak       | Nr              |
|                                      | Eksport danych do własnego magazynu danych                                                    | Tak       | Tak             |
|                                      | Włączenie eksportu aktualizacji przyrostowych do jednostki danych                                 | Tak       | Tak              |
|                                      | Integracje danych                                                                         | Tak       | Tak             |
| Zarządzanie dokumentami                  |                                                                                           | Tak       | Tak             |
| Pomoc                                 |                                                                                           | Tak       | Nie              |
| Analizy                         |                                                                                           | Tak       | Tak             |
|                                      | Raportowanie elektroniczne (ER)                                                                 | Tak       | Tak             |
|                                      | ER: Integracja z LCS                                                                  | Tak       | Nie              |
|                                      | ER: Integracja z SharePoint                                                           | Tak       | Nie              |
|                                      | ER: Integracja z Regulatory Configuration Services (RCS)                              | Tak       | Nie              |
|                                      | ER: używa lokalnego systemu plików jako magazynu na konfiguracje ER dostępne z repozytoriów ER | Nr        | Tak             |
|                                      | Integracja z PowerBI.com                                                              | Tak       | Nr              |
|                                      | Integracja z PowerBI Desktop                                                          | Nr        | Tak             |
|                                      | Analityczne obszary robocze                                                                     | Tak       | Nr              |
|                                      | Inteligentny proces biznesowy: zalecenia                                             | Tak       | Nr              |
|                                      | Tworzenie raportów dla usługi Power BI za pomocą interfejsu OData z wykorzystaniem aplikacji Power BI lub narzędzi PowerQuery dla programu Excel    | Tak       | Nr              |
|                                      | Usługi SQL Server Reporting Services (SSRS) obsługują skalowanie                                 | Tak       | Nr              |
|                                      | Dane telemetryczne są przesyłane do chmury                                                   | Tak       | Nr              |
| Zarządzanie zapasami                 |                                                                                           | Tak       | Tak             |
| Usługi Lifecycle Services                   |                                                                                           | Tak       | Tak             |
|                                      | Konfigurowalne procesy biznesowe                                                           | Tak       | Nr              |
| Lokalizacje                        |                                                                                           | Tak       | Tak             |
| Produkcja                        |                                                                                           | Tak       | Tak             |
| Planowanie główne i prognozy      |                                                                                           | Tak       | Tak             |
| Optymalizacja planowania                |                                                                                           | Tak       | Nr              |
| Aplikacja mobilna, obszary robocze i platforma |                                                                                           | Tak       | Tak             |
| Integracja z pakietem Office                   |                                                                                           | Tak       | Tak             |
| Administrowanie organizacją          |                                                                                           | Tak       | Tak             |
| Zaopatrzenie i sourcing             |                                                                                           | Tak       | Tak             |
|                                      | Korzystanie z katalogu zewnętrznego z zapotrzebowania na zakup                                   | Tak       | Nr              |
|                                      | Raporty Analiza wydatków i zakupów w usłudze Power BI                                                  | Tak       | Nr              |
| Zarządzanie informacjami o produktach       |                                                                                           | Tak       | Tak             |
| Dane produktu głównego                  |                                                                                           | Tak       | Tak             |
| Produkcja                           |                                                                                           | Tak       | Tak             |
|                                      | Raporty Wydajność produkcji w usłudze Power BI                                                   | Tak       | Nr              |
| Zarządzanie projektami i ich księgowanie    |                                                                                           | Tak       | Tak             |
| Sprzedaż                                |                                                                                           | Tak       | Tak             |
|                                      | Raporty Wyniki w zakresie sprzedaży i rentowności w usłudze Power BI                                      | Tak       | Nr              |
| Zabezpieczenia                             |                                                                                           | Tak       | Tak             |
| Zarządzanie serwisem                   |                                                                                           | Tak       | Tak             |
| Zarządzanie łańcuchem dostaw              |                                                                                           | Tak       | Tak             |
| Zarządzanie transportem            |                                                                                           | Tak       | Tak             |
| Współpraca z dostawcami                 |                                                                                           | Tak       | Nr              |
| Zarządzanie magazynem                 |                                                                                           | Tak       | Tak             |
|                                      | Mobilna aplikacja magazynu                                                                      | Tak       | Tak             |
|                                      | Raporty magazynowe w usłudze Power BI                                                              | Tak       | Nr              |
| Klient sieci Web                           |                                                                                           | Tak       | Tak             |
|                                      | Rejestrator zadań — zapisywanie i ładowanie rejestracji zadań z biblioteki BPM                         | Tak       | Nr              |
| Pomoc techniczna                              |                                                                                           | Tak       | Tak             |
|                                      | Dostęp do pomocy technicznej w menu Pomoc i obsługa techniczna                                             | Tak       | Nie              |

## <a name="dynamics-365-commerce"></a>Dynamics 365 Commerce 

Aby wyświetlić listę funkcji dostępnych we wdrożeniach lokalnych, zobacz [Funkcje Commerce dostępne we wdrożeniach lokalnych](../../../retail/retail-onprem.md).

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
|                            | Obsługiwanie środowisk                    | Tak       | Nr              |
| Analizator śledzenia               |                                           | Tak       | Tak             |
| PerfTimer                  |                                           | Tak       | Tak\*           |
| Uaktualnij                    |                                           | Tak       | Tak             |
|                            | Uaktualnij                                   | Tak       | Nr              |
|                            | Uaktualnienie i obsługa wcześniejszych wersji | Tak       | Nr              |
| Programowanie Visual Studio  |                                           | Tak       | Tak             |

\* W środowiskach lokalnych PerfTimer wyświetla tylko wyniki dla klienta.

