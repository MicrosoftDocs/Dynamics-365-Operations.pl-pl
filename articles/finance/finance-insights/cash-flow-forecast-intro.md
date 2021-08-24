---
title: Prognoza przepływów pieniężnych (wersja zapoznawcza)
description: W tym temacie opisano możliwości prognozowania przepływów pieniężnych.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 0ae8dc658cb0bc70cff569542a79196afd2bc1ef5c8ac93470f8233587e2d049
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713835"
---
# <a name="cash-flow-forecast-preview"></a>Prognoza przepływów pieniężnych (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]

Przepływy pieniężne mają podstawowe znaczenie dla każdej firmy. Nawet rentowne firmy mogą być niewypłacalne, jeśli nie utrzymują przepływu pieniężnego na poziomie zaspokajającym bieżące potrzeby. Możliwość prognozowania przepływów pieniężnych w ramach Finance Insights może pomóc firmom w efektywnym monitorowaniu sald środków pieniężnych i zarządzaniu nimi. Ta funkcja korzysta z funkcji uczenia maszynowego, która ułatwia firmom prognozowanie przepływów pieniężnych bardziej dokładnie niż wcześniej. Może również pomagać menedżerom w podejmowaniu decyzji optymalizujących szanse sprzedaży w kontekście ich bieżącego stanu środków pieniężnych. 

W przypadku większości firm zarządzanie przepływem gotówki i uruchamianie prognozowania przepływów pieniężnych jest żmudnym, powtarzającym się i ręcznym procesem. Większość firm opiera się na rozwiązaniach Microsoft Excel o różnych stopniach złożoności. Dokładne prognozowania przepływu pieniężnego może sprawiać trudności z następujących przyczyn:

- Dane nie są dostępne dla osób podejmujących decyzje, ponieważ są rozrzucone w wielu miejscach, w tym: 
  - System księgowo-finansowy lub system planowania zasobów przedsiębiorstwa
  - Oprogramowanie do planowania finansowego
  - Plik programu Excel
  - Dodatkowe aplikacje 
- Prognozowanie opiera się na wewnętrznej bazie wiedzy, która znajduje się w „silosach” należących do poszczególnych domen lub działów.
- Mierzenie dokładności prognozowania przepływów pieniężnych po zrealizowaniu transakcji finansowych jest niepewne i trudne.
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a>Szczegóły możliwości prognoz przepływów pieniężnych
Funkcja prognoz przepływów pieniężnych obejmuje następujące funkcje: 

- Ułatwia integrację danych przepływów pieniężnych z systemów zewnętrznych z systemem Dynamics 365 Finance. Prognozy przepływów pieniężnych mogą również wykorzystywać strukturę importu i eksportu danych. Ta struktura ułatwia integrację z usługą OData dla programu Excel. Można również połączyć dane z wielu źródeł w celu utworzenia wszechstronnego rozwiązania do przepływu pieniężnego. 

- Wprowadza inteligentny stan środków pieniężnych. Stan środków pieniężnych jest tworzony na podstawie zachowań płatności odbiorcy w celu przewidywania, kiedy firma może oczekiwać wpłaty gotówkowej na swoje konta. Ponadto analizuje historyczne wzorce płatności dla dostawców, aby przewidzieć, kiedy zostaną prawdopodobnie zapłacone przyszłe faktury i zamówienia. 

- Wprowadza inteligentne prognozowanie przepływów pieniężnych dla długoterminowej prognozy, używając prognozowania szeregu czasowego poprzez automatyczną integrację z AI Builder.

- Umożliwia zapisywanie konkretnego stanu środków pieniężnych lub ich prognoz, ich edytowanie, a następnie łatwe porównywanie prognozy z rzeczywistymi finansami i mierzenie jej skuteczności.

- Umożliwia analizę warunkową poprzez porównanie migawek. Można na przykład utworzyć wiele migawek reprezentujących optymistyczne, pesymistyczne i najbardziej realistyczne scenariusze przepływów pieniężnych, a następnie porównać i wyświetlić te różnice.

- Umożliwia wyświetlanie prognozy przepływów pieniężnych w wielu walutach, między firmami oraz filtrowanie i wyświetlanie przepływów pieniężnych związanych z kontem bankowym. 

- Umożliwia filtrowanie i wyświetlanie kont bankowych, które są powiązane z wymiarami finansowymi.

Funkcja prognozowania przepływów pieniężnych w systemie Dynamics 365 Finance pozwala organizacji na przekształcanie żmudnych, złożonych i powtarzających się projekcji przepływów pieniężnych w prosty, zautomatyzowany proces. Automatyzacja najbardziej żmudnych aspektów prognozowania przepływów pieniężnych umożliwia skoncentrowanie się na krytycznych decyzjach przekładających się na pożądane wyniki biznesowe.

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a>Konfigurowanie wymiarów dla prognozowania przepływów pieniężnych
Nowa karta na stronie **Konfiguracja prognozowania przepływów pieniężnych** umożliwia kontrolowanie wymiarów finansowych, które mają być używane do filtrowania, w obszarze roboczym **Prognozowanie przepływów pieniężnych**. Ta karta będzie wyświetlana tylko wtedy, gdy jest włączona funkcja prognoz przepływów pieniężnych. 

Na karcie **Wymiary** wybierz z listy wymiary, które mają być użyte do filtrowania, a następnie za pomocą klawiszy strzałek przenieś je do prawej kolumny. Do filtrowania danych prognozy przepływów pieniężnych można wybrać tylko dwa wymiary. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
