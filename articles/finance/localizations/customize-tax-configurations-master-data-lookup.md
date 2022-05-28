---
title: Dostosowywanie konfiguracji podatków do wyszukiwania danych głównych
description: W tym temacie opisano sposób dostosowywania konfiguracji podatków w celu rozszerzenia funkcji wyszukiwania danych głównych.
author: kai-cloud
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 69541316ad4c6c4bb404ea142844ce596b5502b9
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689136"
---
# <a name="customize-tax-configurations-for-master-data-lookup"></a>Dostosowywanie konfiguracji podatków do wyszukiwania danych głównych

[!include [banner](../includes/banner.md)]

Wykonaj kroki z tego tematu, aby dostosować konfigurację podatków w celu rozszerzenia funkcji wyszukiwania danych głównych.

## <a name="import-a-tax-configuration-provided-by-microsoft"></a>Importowanie konfiguracji podatków dostarczanej przez Microsoft

1. W usłudze Regulatory Configuration Service (RCS), w obszarze roboczym **Raportowanie elektroniczne** wybierz **Microsoft** jako dostawcę konfiguracji.
2. Wybierz **Repozytoria**.
3. Wybierz opcję **Globalny**, a następnie wybierz opcję **Otwórz**.
4. Wybierz konfigurację podatku, np. **Konfiguracja obliczania podatku**, a następnie na karcie **Wersje** wybierz wersję.
5. Wybierz opcję **Importuj**.

> [!NOTE]
> Domyślnie mapowanie modelu usługi Dataverse jest importowane. Jeśli podczas procesu importowania konfiguracji są wyświetlane komunikaty ostrzegawcze, włącz encje wirtualne w programie Dataverse. Aby uzyskać więcej informacji, zobacz [Włączanie wirtualnych encji Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="create-a-customized-data-model-configuration"></a>Tworzenie dostosowanej konfiguracji modelu danych

1. W obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Konfiguracje podatku**, a następnie wybierz konfigurację modelu danych do rozszerzenia. Na przykład wybierz opcję **Model danych obliczania podatku**.
2. Wybierz **Utwórz konfigurację**.
3. Wybierz opcję **Model dokumentów podlegających opodatkowaniu uzyskany na podstawie pola Nazwa: Model danych obliczania podatku, Microsoft**.
4. W polu **Nazwa** wpisz **Model danych dostosowywania**.
5. Wybierz **Utwórz konfigurację**.

## <a name="create-customized-reference-models"></a>Tworzenie spersonalizowanych modeli odwołań

1. Na stronie **Konfiguracje podatków** wybierz **Model danych dostosowywania**, a następnie wybierz pozycję **Projektant**.
2. Wybierz przycisk wielokropka (**...**), a następnie wybierz widok **Model odwołania**.

    [![Model odwołania.](./media/pic2.png)](./media/pic2.png)

3. Utwórz dostosowany model odwołania. Model dostosowany jest modelem głównym. Dostosowana encja jest listą rekordów. Dostosowane pole jest polem ciągu, którego chcesz używać w wyszukiwaniach. Możesz dodać więcej pól według potrzeb.
4. Wybierz przycisk wielokropka (**...**), a następnie wybierz widok **Dokument podlegający opodatkowaniu**.
5. Wybierz atrybut, który ma być powiązany z dostosowanym modelem odwołania. Na przykład wybierz **Atrybut dostosowany**, a następnie wykonaj następujące czynności:

    1. Wybierz opcję **Wybierz model odwołania**.
    2. Wybierz pozycję **Model dostosowany**, a następnie wybierz przycisk **OK**. Nazwa modelu odwołania jest aktualizowana wartością pola **Klucz naturalny**.

        [![Okno dialogowe Wybieranie modelu odwołania.](./media/pic5.png)](./media/pic5.png)

    3. Wybierz **Zapisz** i następnie wybierz **Zakończ**.

## <a name="create-a-customized-model-mapping-configuration"></a>Tworzenie dostosowanej konfiguracji mapowania modelu

1. W obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Konfiguracje podatku**, a następnie wybierz konfigurację **modelu mapowania Dataverse**.
2. W polu **Domyślne dla mapowania modelu** wybierz opcję **Nie**.
3. Wybierz **Utwórz konfigurację**.
4. Wybierz opcję **Mapowanie modelu dokumentów podlegających opodatkowaniu uzyskane na podstawie pola Nazwa: Mapowanie modelu usługi Dataverse, Microsoft**.
5. W polu **Nazwa** wpisz **Mapowanie modelu dostosowywania**.
6. W polu **Model docelowy** wybierz model danych **Model danych dostosowywania**.
7. Wybierz **Utwórz konfigurację**.

    [![Utwórz okno dialogowe tworzenia konfiguracji.](./media/pic6.png)](./media/pic6.png)

8. Wybierz **mapowanie modelu dostosowywania** i ustaw pole **Połączona aplikacja** na połączenie utworzone w kroku 8 w sekcji [Konfigurowanie środowiska wyszukiwania danych głównych](tax-service-set-up-environment-master-data-lookup.md).
9. Ustaw pole **domyślnego mapowania modelu** jako **Tak**.

## <a name="create-customized-model-mappings"></a>Tworzenie dostosowanych mapowań modeli

1. Na stronie **Konfiguracje podatków** wybierz opcję **Mapowanie modelu dostosowywania**.
2. Wybierz pozycję **Projektant**, a następnie wybierz **Model dostosowywania**.

    [![Model dostosowywania.](./media/pic8.png)](./media/pic8.png)

## <a name="map-a-model-mapping-to-a-dataverse-entity"></a>Mapowanie mapowania modelu na encję usługi Dataverse

1. Na stronie **Projektant mapowania modelu** wybierz **Model dostosowywania**, a następnie wybierz pozycję **Projektant**.
2. W drzewie **Typy źródła danych** wybierz opcję **Tabele usługi Dataverse**.
3. Na karcie **Źródła danych** wybierz **Dodaj źródło**.
4. W polu **Nazwa** wprowadź **Dostosowana usługa Dataverse**.
5. W drugim polu **Nazwa** wybierz encję.
6. Kliknij przycisk **OK**.

    [![Okno dialogowe Właściwości źródła danych „Tabela”.](./media/pic9.png)](./media/pic9.png)

7. Wybierz opcję **Dostosowana usługa Dataverse** i **Dostosowana encja**, a następnie opcję **Powiąż**.

    [![Tworzenie powiązania dostosowanej usługi Dataverse i dostosowanej encji.](./media/pic10.png)](./media/pic10.png)

8. W obszarze **Dostosowana usługa Dataverse** i **Dostosowane pole** wybierz pole, a następnie opcję **Powiąż**.

    [![Tworzenie powiązania dostosowanej usługi Dataverse i dostosowanego pola.](./media/pic11.png)](./media/pic11.png)

9. Wybierz **Zapisz** i następnie wybierz **Zakończ**.

## <a name="create-a-customized-tax-configuration"></a>Tworzenie dostosowanej konfiguracji podatku

1. W obszarze roboczym **Raportowanie elektroniczne** wybierz opcję **Konfiguracje podatku**, a następnie wybierz **konfigurację obliczania podatku**.
2. Wybierz **Utwórz konfigurację**.
3. Wybierz opcję **Konfigurację usługi podatku pochodząca z pola Nazwa: Konfiguracja obliczania podatku, Microsoft**.
4. W polu **Nazwa** wpisz **Konfiguracja dostosowywania**.
5. Wybierz **Utwórz konfigurację**.
6. Wybierz pozycję **Konfiguracja dostosowywania**, a następnie wybierz **Projektant**.
7. W polu **Model danych** wybierz pozycję **Model danych dostosowywania**.
8. W polu **Wersja modelu danych** wybierz wersję odpowiadającą modelowi danych.

    [![Sekcja Właściwości.](./media/pic13.png)](./media/pic13.png)

9. Wybierz opcję **Zakończone**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
