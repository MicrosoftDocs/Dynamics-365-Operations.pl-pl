---
title: Używanie ścieżki względnej w powiązaniach danych z modelami i formatami ER
description: Narzędzie Raportowanie elektroniczne pozwala Ci definiować struktury formatu elektronicznego, a następnie opisywać, jak te struktury powinny być wypełniane.
author: NickSelin
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 686600e857c7b5aab74d80b7bc31c6bbaaf8d2336d57ff5839752d0ff33def84
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741687"
---
# <a name="use-a-relative-path-in-data-bindings-of-er-models-and-formats"></a>Używanie ścieżki względnej w powiązaniach danych z modelami i formatami ER

[!include[banner](../includes/banner.md)]

Narzędzie raportowanie elektroniczne (ER) pozwala użytkownikom definiować struktury formatu elektronicznego, a następnie opisywać, jak te struktury powinny być wypełniane przy użyciu danych i algorytmów, które znajdują się w aplikacji. Aby uzyskać więcej informacji, zobacz [Tworzenie konfiguracji raportowania elektronicznego (ER)](electronic-reporting-configuration.md). Aby określić przepływ danych służący do pobierania danych Finance and Operations oraz używania go do generowania dokumentu elektronicznego, należy wykonać następujące czynności:

- Powiązanie skonfigurowanych źródeł danych z elementami zaprojektowanego i specyficznego dla domeny [modelu danych](general-electronic-reporting.md#data-model-and-model-mapping-components). Struktura modelu i wybrane źródła danych mogą być częścią złożonej struktury hierarchicznej. Z tego względu ostateczne powiązania mogą być dość duże i mogą zawierać wiele elementów różnych typów (np. relacje, tabele i metody). Powiązania mogą być mniej czytelne i dość skomplikowane do przeglądania i zrozumienia, szczególnie dla osób niebędących właścicielami. 
- Powiązanie elementów modelu danych ze składnikami [formatu](general-electronic-reporting.md#FormatComponentOutbound) w celu zdefiniowania danych, które będą wypełniane z modelu danych do danych wyjściowych wygenerowanego formatu.

Funkcja [ścieżki względnej](er-formula-language.md#relative-path) została wprowadzona, aby poprawić użyteczność projektantów mapowania ER. Domyślnie opcja reprezentacji ścieżki względnej jest włączona dla każdego nowego wystąpienia aplikacji, w których jest włączona funkcja projektowania raportowania elektronicznego ( Microsoft Dynamics 365 Finance, Microsoft Regulatory Configuration Service). Zaimplementowano parametr ścieżki względnej, dzięki czemu użytkownicy mogą nadal korzystać z pełnej ścieżki podczas pracy z tą prezentacją powiązań ER.

[![Parametry użytkownika.](./media/relative-path-01.png)](./media/relative-path-01.png)

 
Po włączeniu parametru użycie ścieżki względnej jeden znak @ zastępuje ścieżkę do elementu nadrzędnego w powiązaniu bieżącego elementu modelu. Cała ścieżka powiązania jest krótsza, co sprawia, że całe mapowanie jest bardziej oczywiste i bardziej zrozumiałe. W większości przypadków nie jest wymagane dodatkowe przewijanie w projektancie ER, aby wyświetlić wszystkie powiązania modelu danych.

[![Projektant mapowania modeli.](./media/relative-path-02.png)](./media/relative-path-02.png)
 
Po rozpoczęciu projektowania nowego wyrażenia ER należy wprowadzić tylko jeden znak, aby zdefiniować powiązanie z polem elementu nadrzędnego.

[![Projektant formuł.](./media/relative-path-03.png)](./media/relative-path-03.png)
 
Jeśli użytkownik zdecyduje się na zmianę źródła danych nadrzędnego elementu modelu, przy użyciu ścieżki bezwzględnej, musi ręcznie ponownie powiązać ten element modelu oraz wszystkie zagnieżdżone elementy z nowym źródłem danych. Jeśli jest włączone użycie ścieżki względnej, a wybrano nowe źródło danych, które ma być powiązane z elementem nadrzędnym, proponowana jest opcja automatycznego powiązania wszystkich zagnieżdżonych elementów tego elementu nadrzędnego z jednym kliknięciem.

[![Zamień istniejący komunikat ścieżki.](./media/relative-path-04.png)](./media/relative-path-04.png)
 
W przypadku potwierdzenia ponownego wiązania zagnieżdżonych elementów, nowy element nadrzędny zostanie umieszczony w ścieżce każdego zagnieżdżonego elementu zawierającego istniejący element nadrzędny.
Ta funkcja nie powoduje przerwy w zgodności z poprzednimi wersjami platformy ER. Wszystkie uprzednio zaprojektowane konfiguracje funkcji ER będą działać z tą nową funkcją i nie są wymagane żadne uaktualnienia ani konwersje.

> [!NOTE]
> Wszystkie zmiany wprowadzone przez grupowe modyfikacje powiązań zagnieżdżonych elementów w mapowaniu modeli są poprawnie zapisane w delcie konfiguracji (śledzenie zmian). Dzięki temu klienci mogą zmienić pochodną wersję mapowań modeli na dowolną nową wersję podstawową, która została zmodyfikowana za pomocą tej nowej funkcji.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Język formuł ER](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]