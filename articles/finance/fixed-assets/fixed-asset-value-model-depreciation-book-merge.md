---
title: Scalenie funkcjonalności modeli ewidencji i księgi amortyzacji środków trwałych
description: 'W poprzednich wersjach istniały dwie koncepcje wyceny środków trwałych: modele ewidencji i księgi amortyzacji. W programie Microsoft Dynamics 365 for Operations (wydanie 1611) funkcje modeli ewidencji i ksiąg amortyzacji zostały scalone w pojedynczy obiekt zwany księgą.'
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3225b214e729ff13d4ffe8ad1d8cf0f2d6baae49
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446688"
---
# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Scalenie funkcjonalności modeli ewidencji i księgi amortyzacji środków trwałych

[!include [banner](../includes/banner.md)]

W poprzednich wersjach istniały dwie koncepcje wyceny środków trwałych: modele ewidencji i księgi amortyzacji. W programie Microsoft Dynamics 365 for Operations (wydanie 1611) funkcje modeli ewidencji i ksiąg amortyzacji zostały scalone w pojedynczy obiekt zwany księgą.

Nowa funkcjonalność księgi opiera się na wcześniejszej funkcjonalności modelu ewidencji, ale także zawiera wszystkie funkcje dostępne wcześniej tylko w księgach amortyzacji. [![Księga jako narzędzie powstałe ze scalenia modeli ewidencji i ksiąg amortyzacji](./media/fixed-assets.png)](./media/fixed-assets.png) Ze względu na to scalenie można teraz używać jednego zbioru stron, zapytań i raportów dla wszystkich procesów związanych ze środkami trwałymi. Tabele w tym temacie opisują wcześniejsze funkcje ksiąg amortyzacji i modeli ewidencji oraz nową funkcjonalność ksiąg.

## <a name="setup"></a>Konfiguracja
Domyślnie zapisy ksiąg są księgowane do księgi głównej (KG) i księgi podrzędnej środków trwałych. Księgi mają nową funkcję **Księguj w księdze głównej**, która pozwala wyłączyć księgowanie w księdze głównej i księgować tylko w księdze podrzędnej środków trwałych. Ta funkcja jest podobna do wcześniejszego zachowania funkcji księgowania stosowanego w księgach amortyzacji. Konfiguracja arkuszy ma nową warstwę księgowania o nazwie Brak. Tę warstwę księgowania dodano specjalnie dla transakcji na środkach trwałych. Aby zaksięgować transakcje dla ksiąg, które nie księgują w KG, należy użyć arkusza, w którym została ustawiona warstwa księgowania **Brak**.

|                                                  |                                 |                                 |                                                         |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
|                                                  | Księga amortyzacji               | Model ewidencji                     | Księga (nowa)                                              |
| Księgowanie w KG                                   | Nigdy                           | Zawsze                          | Opcja księgowania w KG                                |
| Warstwy księgowania                                   | Nie dotyczy                  | 3: Bieżący, Operacje i Podatek | 11: Bieżący, Operacje, Podatek, 7 warstw niestandardowych i Brak |
| Nazwy arkuszy                                    | Nazwy arkuszy księgi amortyzacji | KG — Nazwy arkuszy              | KG — Nazwy arkuszy                                      |
| Księgi pochodne                                    | Niedozwolone                     | Dozwolone                         | Dozwolone                                                 |
| Zastąpienie profilu amortyzacji na poziomie składnika aktywów | Dozwolone                         | Niedozwolone                     | Dozwolone                                                 |

## <a name="processes"></a>Procesy
Teraz procesy używają wspólnej strony. Niektóre procesy są dozwolone tylko wtedy, gdy w konfiguracji księgi opcja **Księguj w księdze głównej** ma ustawioną wartość **Nie**.

|                                |                           |                     |                                          |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
|                                | Księga amortyzacji         | Model ewidencji         | Księga (nowa)                               |
| Wprowadzanie transakcji              | Arkusz księgi amortyzacji | Arkusz środków trwałych | Arkusz środków trwałych                      |
| Podwyższenie amortyzacji             | Dozwolone                   | Niedozwolone         | Dozwolone                                  |
| Usuwanie historycznych transakcji | Dozwolone                   | Niedozwolone         | Dozwolone, chyba że księgujesz w KG |
| Aktualizacja grupowa                    | Dozwolone                   | Niedozwolone         | Dozwolone, chyba że księgujesz w KG |

## <a name="inquiries-and-reports"></a>Zapytania i raporty
Zapytania i raporty obsługują wszystkie księgi. Raporty, które nie są uwzględnione w tabeli poniżej, wcześniej obsługiwały modele ewidencji i księgi amortyzacji, i teraz nadal będą obsługiwały wszystkie typy ksiąg. Do raportów również zostało dodane pole **Warstwa księgowania**, dzięki czemu można łatwiej rozpoznać księgowania transakcji.

|                                       |                                |                          |                          |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
|                                       | Księga amortyzacji              | Model ewidencji              | Księga (nowa)               |
| Zapytania                             | Transakcje księgi amortyzacji | Transakcje środków trwałych | Transakcje środków trwałych |
| Zestawienie środków trwałych                 | Niedozwolone                    | Dozwolone                  | Dozwolone                  |
| Podstawa środka trwałego                     | Dozwolone                        | Niedozwolone              | Dozwolone                  |
| Możliwość zastosowania środka trwałego w trakcie kwartału | Dozwolone                        | Niedozwolone              | Dozwolone                  |

## <a name="upgrade"></a>Uaktualnienie
Proces uaktualniania spowoduje przeniesienie istniejących ustawień i wszystkich istniejących transakcji do nowej struktury księgi. Modele ewidencji pozostaną w swoim obecnym kształcie, jako księgi powodujące księgowanie w księdze głównej. Natomiast księgi amortyzacji zostaną przeniesione do księgi, która w opcji **Księguj w księdze głównej** ma wartość **Nie**. Arkusze ksiąg amortyzacji zostaną przeniesiona do arkusza księgi głównej, w której ustawiono warstwę księgowania **Brak**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]