---
title: Wdrażanie rozwiązania IoT w Azure
description: Usługa Sensor Data Intelligence używa danych z czujników, które są połączone z usługą Microsoft Azure. W tym artykule opisano, jak wdrożyć rozwiązanie Internet rzeczy (IoT) w subskrypcji systemu Azure.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreAzureResourceDeploymentWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 284aba91aa436ed1dfc02b5a93b4358ffc518017
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428472"
---
# <a name="deploy-an-iot-solution-on-azure"></a>Wdrażanie rozwiązania IoT w Azure

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Usługa Sensor Data Intelligence używa danych z czujników, które są połączone z usługą Microsoft Azure. Aby umożliwić systemowi Azure pobieranie danych z czujników i udostępnianie ich rozwiązaniu Dynamics 365 Supply Chain Management, musisz wdrożyć rozwiązanie Internetu rzeczy (IoT) w subskrypcji systemu Azure. Poniższy diagram architektury zawiera omówienie rozwiązania i jego składników.

![Diagram architektury Sensor Data Intelligence.](media/sdi-architecture.png "Diagram architektury Sensor Data Intelligence")

Wykonaj następujące kroki, aby wdrożyć wymagane zasoby w usłudze Azure.

1. Zaloguj się do Supply Chain Management jako administrator.
1. Przejdź do narzędzia **Administracja systemu \> Konfiguracja \> Sensor Data Intelligence \> Wdróż i połącz zasoby Azure**, aby otworzyć kreatora wdrażania.
1. Na stronie **Witamy**, przeczytaj informacje i wybierz przycisk **Dalej**.
1. Na stronie **Wdróż przykładowe rozwiązanie IoT w Azure** przeczytaj informacje, a następnie w sekcji **Instrukcje** wybierz pozycję **Wdróż**.
1. Zostanie otwarta nowa karta przeglądarki i użytkownik zostanie przeniesiony do portalu Azure Portal, aby można było wdrożyć zasoby systemu Azure. Jeśli zostanie wyświetlony monit, zaloguj się, używając swoich poświadczeń dla subskrypcji systemu Azure.
1. Na stronie **Niestandardowe wdrożenie** w polu **Subskrypcja** wybierz swoją subskrypcję.
1. W polu **Grupa zasobów** wybierz pozycję **Utwórz nowe**, aby utworzyć grupę zasobów dla składników systemu Azure, które zostaną wdrożone.
1. W oknie rozwijaym, które zostanie wyświetlone, w polu **Nazwa**, wprowadź nazwę nowej grupy zasobów (na przykład *IoT-demo*). Następnie wybierz opcję **OK**.
1. Ustaw wartości w następujących polach:

    - **Grupa zasobów** — umożliwia wybór właśnie utworzonej grupy zasobów.
    - **Region** — umożliwia wybór regionu, najlepiej regionu, w którym jest wdrożone środowisko Supply Chain Management. Pamiętaj, że regiony systemu Azure mają różne ceny. Szacowane koszty dla regionu można wyświetlać za pomocą [kalkulatora cen Sensor Data Intelligence](https://azure.com/e/c36c4947ebff4215b2e62590c2a24c68).
    - **Adres URL środowiska Supply Chain Management** — wprowadź adres URL środowiska Supply Chain Management
    - **Ponowne użycie istniejącego centrum Azure IoT Hub** — pozostaw to pole wyboru wyczyszone.

1. Wybierz opcję **Dalej: przejrzyj + utwórz**.
1. Na stronie **Wdrożenie niestandardowe** sprawdź, czy walidacja zakończyła się pomyślnie, a następnie wybierz pozycję **Utwórz**.
1. Strona **Wdrażanie jest w toku** śledzi postęp wdrażania. Proces wdrażania może potrwać do 30 minut. Jeśli strona **Wdrażanie jest w toku** wskazuje, że wdrażanie się zakończyło, wybierz łącze dla nazwy grupy zasobów, aby otworzyć stronę, która pokazuje listę zasobów wdrożonych w grupie.
1. Na liście zasobów znajdź rekord, w którym pole **Typ** jest ustawione na centrum *Tożsamość zarządzana*. Wybierz wartość w kolumnie **Nazwa**, wybierz nazwę, aby otworzyć stronę szczegółów dla zasobu.
1. Kopiuj wartość pola **Identyfikator klienta** (na przykład przez wybranie przycisku **Kopiuj do Schowka**).
1. Wróć na kartę przeglądarki, na której jest uruchomione Supply Chain Management, *ale nie zamykaj karty portalu Azure Portal*. Strona kreatora **Wdróż przykładowe rozwiązanie IoT w Azure** powinna być nadal otwarta. 
1. Wybierz pozycję **Następny**.
1. Na stronie **Połącz zasoby systemu Azure** w polu **Identyfikator klienta Azure AD** wklej skopiowaną wartość **Identyfikatora klienta**.
1. Wróć na kartę przeglądarki, na której jest otwarty Azure Portal, *ale nie zamykaj karty Supply Chain Management*. Strona szczegółów dla zasobu powinna pozostać otwarta.
1. Wybierz przycisk **Wstecz** przeglądarki, aby powrócić do listy zasobów w nowej grupie zasobów.
1. Na liście zasobów znajdź rekord, w którym pole **Typ** jest ustawione na *Azure Cache for Redis*. Wybierz wartość w kolumnie **Nazwa**, wybierz nazwę, aby otworzyć stronę szczegółów dla zasobu.
1. W okienku nawigacji po lewej stronie wybierz pozycję **Klucze dostępu**.
1. Na stronie **Klucze dostępu** skopiuj wartość wyświetlaną dla **Ciągu połączenia podstawowego (StackExchange.Redis)** (na przykład przez wybranie przycisku **Kopiuj do Schowka**).
1. Wróć do karty przeglądarki, na której jest uruchomione Supply Chain Management. Strona **Połącz zasoby systemu Azure** musi być nadal otwarta.
1. W polu **Ciąg połączenia magazynu metryk Redis** wklej skopiowaną wartość **Ciąg połączenia podstawowego (StackExchange.Redis)**.
1. Wybierz **Zakończ**.

Zasoby systemu Azure dla Sensor Data Intelligence zostały teraz wdrożone w subskrypcji systemu Azure.

> [!NOTE]
> W dowolnym momencie można wyświetlić lub zmodyfikować informacje o połączeniu zapisane w Supply Chain Management, otwierając stronę **Parametry Sensor Data Intelligence**. Aby uzyskać więcej informacji, zobacz [Parametry Sensor Data Intelligence](sdi-parameters.md).
