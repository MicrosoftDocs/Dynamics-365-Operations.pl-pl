---
title: Tworzenie nowego aparatu zarządzania transportem
description: W tym artykule opisano sposób tworzenia nowego aparatu zarządzania transportem w aplikacji Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSGenericEngine, TMSRateEngine, TMSMileageEngine, TMSEngineParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 51661
ms.assetid: 0473acef-755e-4b42-acf5-5e5aa902dc0e
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 627972ef6afb7551bb57821ded24183f8f335e9b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857265"
---
# <a name="create-a-new-transportation-management-engine"></a>Tworzenie nowego aparatu zarządzania transportem

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób tworzenia nowego aparatu zarządzania transportem w aplikacji Dynamics 365 Supply Chain Management. 

Aparaty zarządzania transportem (TMS) definiują logikę, która służy do tworzenia i przetwarzania stawek transportowych w module Zarządzanie transportem. Aplikacja Supply Chain Management udostępnia kilka różnych typów aparatów, które obliczają różne parametry, takie jak stawki, czasy tranzytu oraz liczba stref, które będą przekraczane podczas tranzytu. W tym artykule opisano, jak używać środowiska developmentu Microsoft Visual Studio wraz z narzędziami dewelopera w aplikacji Supply Chain Management w celu utworzenia i wdrożenia nowego aparatu TMS, a następnie skonfigurowania aparat w aplikacji Operations. Aby uzyskać więcej informacji o aparatach, zobacz temat [Aparaty zarządzania transportem](transportation-management-engines.md).

## <a name="create-a-new-tms-engine"></a>Tworzenie nowego aparatu TMS

W tej sekcji opisano, jak utworzyć bibliotekę klas, która ma implementację aparatu TMS, oraz jak odwołać się do niego z modelu aplikacji Supply Chain Management.

1. Aby można było wdrożyć nowe aparaty, musisz mieć model, który będzie zawierał aparaty. W menu **Dynamics 365** &gt; **Zarządzanie modelami** kliknij pozycję **Utwórz model**, aby utworzyć nowy model. Na pierwszej stronie kreatora **tworzenia modelu** nazwij model **TMSEngines**. 

   [![Tworzenie modelu.](./media/012.png)](./media/012.png)

2. Na następnej stronie wybierz pozycję **Utwórz nowy pakiet**. 

   [![Tworzenie nowego pakietu.](./media/021.png)](./media/021.png)

3. Na następnej stronie wybierz model **ApplicationSuite** na potrzeby odwołania. (Model **ApplicationPlatform** jest wstępnie wybrany). 

   [![Wybór modelu do odwołania.](./media/032.png)](./media/032.png)

4. Na następnej stronie kliknij przycisk **Zakończ**, aby potwierdzić utworzenie nowego modelu. 

   [![Kończenie tworzenia modelu.](./media/042.png)](./media/042.png)

5. W nowym rozwiązaniu utwórz nowy projekt Supply Chain Management i nazwij go **TMSThirdParty**. We właściwościach projektu ustaw model projektu na **TMSEngines**.
6. Dodaj nową bibliotekę klas C\# do rozwiązania i nadaj jej nazwę **ThirdPartyTMSEngines**.
7. W projekcie ThirdPartyTMSEngines dodaj odwołania do zestawów specyficznych dla aplikacji Supply Chain Management:
   -   Zestawy aplikacji, które umożliwiają odwołanie do typów X++. Zestawy te można znaleźć w następujących lokalizacjach. \[Katalog główny pakietów\] to ścieżka do lokalizacji, w której znajdują się wszystkie wdrożone zestawy, na przykład C:\\Packages.

        ```xpp
        [Packages root]\ApplicationPlatform\bin\Dynamics.AX.ApplicationPlatform.dll
        [Packages root]\ApplicationFoundation\bin\Dynamics.AX.ApplicationFoundation.dll
        [Packages root]\ApplicationSuite\bin\Dynamics.AX.ApplicationSuite.dll
        ```
        
   -   Zestawy struktury umożliwiające dostęp do danych, usług LINQ i funkcji pomocniczych. Wszystkie te zestawy można znaleźć w zasobniku \[Katalog główny pakietów\]\\.

        ```xpp 
        Microsoft.Dynamics.ApplicationPlatform.Environment.dll
        Microsoft.Dynamics.AX.Data.Core.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.AdoNet.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Interface.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Msil.dll
        Microsoft.Dynamics.AX.Server.Core.dll
        Microsoft.Dynamics.AX.Xpp.AxShared.dll
        Microsoft.Dynamics.AX.Xpp.Support.dll
        ```

   -   Podstawowy zestaw TMS (zawierający aparaty) i bazowy zestaw TMS (zawierający pomocników, stałe, definicje klas transferu danych itp.). Zestawy te można znaleźć w następujących lokalizacjach.

        ```xpp
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.dll
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.Base.dll
        ```
8. Zmień nazwę klasy C\# generowanej automatycznie w projekcie ThirdPartyTMSEngines na **SampleRatingEngine**.
9. Zaimplementuj aparat. Ponieważ w tym przykładzie tworzymy aparat stawki, dziedziczymy po klasie bazowej dla aparatów stawek. Klasa bazowa implementuje większość interfejsu aparatu stawki (**TMSFwkIRateEngine**). Wystarczy wdrożyć metodę stawek. Aby zachować ten przykład jako prosty, spowodujemy, że metoda zarejestruje zakodowaną na stałe stawkę 100. Można tworzyć aparaty implementują dowolne interfejsy aparatu, takie jak **TMSFwkIAccessorialEngine**. Wszystkie interfejsy aparatu są zdefiniowane w języku X++.

    ```xpp
    namespace ThirdPartyTMSEngines
    {
        using Dynamics.AX.Application;
        using Microsoft.Dynamics.Ax.Tms.Base.Data;
        using Microsoft.Dynamics.Ax.Tms.Base.Utility;
        using Microsoft.Dynamics.Ax.Tms.Bll;
        using System.Xml.Linq;
        public class SampleRatingEngine : BaseRateEngine
        {
            public override RatingDto rate(TmsTransactionFacade transactionFacade, XElement shipment, TMSRateMasterCode rateMasterCode)
            {
               XElement re = shipment.RetrieveOrCreateRatingEntity(this.RatingDto);
               re.AddRate(TmsRateType.Rate, 100);
               return this.RatingDto;
            }
        }
    }
    ```

10. Stwórz rozwiązanie.
11. Dodaj nowe odwołanie do projektu TMSThirdParty. Odwołanie powinno wskazywać na projekt ThirdPartyTMSEngines. Po zakończeniu pracy Twoje rozwiązanie powinno wyglądać tak. 

    [![Rozwiązanie, które zawiera odwołanie do projektu TMSThirdParty.](./media/052.png)](./media/052.png)

12. Stwórz rozwiązanie. Sprawdź, czy nowa biblioteka pojawia się w węźle **Odwołania** w Eksploratorze aplikacji. 

    [![Nowa biblioteka w węźle Odwołania Eksploratora aplikacji.](./media/061.png)](./media/061.png)

## <a name="deploy-the-tms-engine-as-a-package"></a>Wdrożenie aparatu TMS jako pakietu

Jednym ze sposobów wdrażania aparatów TMS innych firm jest pakiet wdrożenia. To podejście jest zalecane w środowisku produkcyjnym. W środowisku developmentu można ręcznie skopiować zestawy w sposób opisany w następnej sekcji „Konfigurowanie aparatu TMS w aplikacji Supply Chain Management”. Aby wdrożyć aparat jako pakiet, wykonaj następujące kroki.

1. W menu **Dynamics 365** &gt; **Wdróż** kliknij pozycję <strong>Utwórz pakiet wdrożenia</strong>.
2. W oknie dialogowym **tworzenia pakietu wdrożenia** wybierz model TMSEngines i wprowadź ścieżkę, w której mają być przechowywane pliki pakietu. 

   [![Wybieranie modelu TMSEngines.](./media/071.png)](./media/071.png)

3. Możesz teraz wdrożyć pakiet w środowisku docelowym. Aby uzyskać samouczek, zobacz temat [Instalowanie wdrażalnego pakietu](../../fin-ops-core/dev-itpro/deployment/install-deployable-package.md).

## <a name="set-up-the-tms-engine-in-supply-chain-management"></a>Konfigurowanie aparatu TMS w aplikacji Supply Chain Management

W tej sekcji opisano sposób konfigurowania aplikacji Supply Chain Management w taki sposób, aby używać aparatu TMS, oraz przedstawiono sposób wykorzystania nowo utworzonego aparatu w procesie wyszukania stawek. W przykładzie w tej sekcji użyto pokazowych danych firmy USMF.

1. Utwórz nowy aparat, tak jak opisano w sekcji „Tworzenie nowego aparatu TMS”.
2. Skompiluj rozwiązanie.
3. Skopiuj wynikowy zestaw do lokalizacji binarnej serwera aplikacji Supply Chain Management, czyli zasobnika \[AOSWebRoot\]. **Uwaga:** ten krok jest odpowiedni tylko w środowisku developmentu. W środowisku produkcyjnym należy wdrożyć za pomocą pakietu wdrożenia. Aby uzyskać instrukcje, zobacz poprzednią sekcję „ Wdrażanie aparatu TMS jako pakietu”.
4. W aplikacji Supply Chain Management na stronie **Aparaty stawek** utwórz nowy aparat oceniania. Aparat powinien wskazać zestaw aparatu, który jest produkowany przez tworzenie biblioteki klas aparatu i zaimplementowanej klasy aparatu. 

   [![Tworzenie nowego aparatu oceniania na stronie Aparaty stawek.](./media/081.png)](./media/081.png)

5. Utwórz przewoźnika, który używa przykładowego aparatu stawki. Ponieważ nasz aparat nie używa żadnych danych, nie trzeba przypisywać głównej stawki. 

   [![Tworzenie nowego przewoźnika.](./media/092.png)](./media/092.png)

6. Na stronie **Pulpit ustalania stawek i wyznaczania tras** kliknij pozycję **Szukanie najlepszej stawki**. Przewoźnik SampleCarrier powinien mieć stawkę 100,00, tak jak pokazano w poniższym zrzucie ekranu. W tym przykładzie szukamy najlepszej stawki dla trasy z magazynu 24 do odbiorcy US-004. Jednak ponieważ stawka jest zakodowana na stałe, zawsze będzie widać stawkę 100,00.

   [![Pulpit ustalania stawek i wyznaczania tras.](./media/101.png)](./media/101.png)

## <a name="tips-and-tricks"></a>Porady i wskazówki

- Jeśli używasz narzędzi deweloperskich w aplikacji Supply Chain Management, warto dodać nowy projekt do rozwiązania. Jeśli projekt zostanie ustawiony jako projekt startowy i rozpocznie się sesja debugowania, można debugować kod X++ i C\# w tej samej sesji debugowania.
- Za każdym razem, gdy zmieniasz i ponownie kompilujesz projekt ThirdPartyTMSEngines, musisz ręcznie skopiować wynikowy zestaw do lokalizacji binarnej lub wdrożyć za pomocą pakietu wdrożenia. W przeciwnym razie możesz uruchomić przy użyciu starego zestawu.
- Po wykonaniu operacji specyficznych dla TMS w aplikacji Supply Chain Management proces roboczy Internetowych usług informacyjnych (IIS) może zablokować zestaw ThirdPartyTMSEngines, aby nie można było go zaktualizować. W takim przypadku uruchom ponownie proces w3svc.

### <a name="whitepaper"></a>Oficjalny dokument

Aby uzyskać więcej informacji, pobierz następujący oficjalny dokument (napisany w celu obsługi systemu AX2012, ale nadal dotyczy aplikacji Dynamics 365 Supply Chain Management)

- [Implementowanie i wdrażanie aparatów zarządzania transportem](https://download.microsoft.com/download/b/5/f/b5ff8fef-3918-4c1d-92d5-b67eb0971684/ImplementingAndDeployingTransportationManagementEnginesInAX.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]