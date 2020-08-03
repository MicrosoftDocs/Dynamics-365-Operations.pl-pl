---
title: Ustawienia scenariusza dla analizy Internetu rzeczy (IoT)
description: W tym temacie opisano sposób konfigurowania scenariusza w aplikacji Supply Chain Management dla analizy Internetu rzeczy (IoT).
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5633741fcd9c04b68e5b174447d7ead3c521ccd7
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597175"
---
# <a name="scenario-setup-for-iot-intelligence"></a><span data-ttu-id="49b7b-103">Ustawienia scenariusza dla analizy Internetu rzeczy (IoT)</span><span class="sxs-lookup"><span data-stu-id="49b7b-103">Scenario setup for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="49b7b-104">W tym temacie opisano sposób konfigurowania scenariusza w aplikacji Supply Chain Management dla analizy Internetu rzeczy (IoT).</span><span class="sxs-lookup"><span data-stu-id="49b7b-104">This topic describes how to configure a scenario in Supply Chain Management for IoT Intelligence.</span></span> <span data-ttu-id="49b7b-105">Aby można było skonfigurować scenariusze, musisz [skonfigurować usługi LCS](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="49b7b-105">Before you can setup the scenarios, you must [setup LCS](iot-lcs-setup.md).</span></span>

<span data-ttu-id="49b7b-106">W tym temacie skonfigurujesz scenariusz **przestoju sprzętu** w celu wygenerowania powiadomienia w aplikacji Supply Chain Management w przypadku awarii urządzenia.</span><span class="sxs-lookup"><span data-stu-id="49b7b-106">In this topic, you will configure the **Equipment downtime** scenario to generate a notification in Supply Chain Management when a machine goes down.</span></span>

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a><span data-ttu-id="49b7b-107">Konfigurowanie scenariusza **przestoju sprzętu** w aplikacji Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="49b7b-107">Configure the **Equipment downtime** scenario in Supply Chain Management</span></span>

<span data-ttu-id="49b7b-108">Scenariusz **przestoju sprzętu** mapuje sygnał oznaczający uszkodzenie części na próg alertu urządzenia.</span><span class="sxs-lookup"><span data-stu-id="49b7b-108">The **Equipment downtime** scenario maps a part out signal to a machine alert threshold.</span></span> <span data-ttu-id="49b7b-109">Urządzenie jest monitorowane tylko wtedy, gdy zostanie wybrane dla scenariusza i ustawione do uruchamiania w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="49b7b-109">The machine is monitored only when the machine is selected for the scenario and is set to running in Supply Chain Management.</span></span> <span data-ttu-id="49b7b-110">Jeśli czas, który upłynął od ostatniego odebrania sygnału oznaczającego uszkodzenie części, jest większy niż próg alertu, zostanie wyzwolone powiadomienie informujące o tym, że **urządzenie nie działa**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-110">If the time since the machine’s last received Part Out signal is greater than the alert threshold, then a **Machine down** notification is triggered.</span></span> <span data-ttu-id="49b7b-111">Jeśli urządzenie nadal działa, po odebraniu następnego sygnału **PartOut** zostanie wyzwolone powiadomienie informujące o tym, że **urządzenie działa**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-111">If the machine is still running, when the next **PartOut** signal is received a **Machine up** notification is triggered.</span></span> <span data-ttu-id="49b7b-112">Jeśli urządzeni nie działa przez 30 minut, jest wyzwalane nowe powiadomienie o tym, że **urządzenie nie działa**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-112">If a machine stays down for 30 mins a new **Machine down** notification is triggered.</span></span>

<span data-ttu-id="49b7b-113">Scenariusz **przestoju sprzętu** obejmuje następujące zależności:</span><span class="sxs-lookup"><span data-stu-id="49b7b-113">The **Equipment downtime** scenario has these dependencies:</span></span>

+ <span data-ttu-id="49b7b-114">W celu wyzwolenia alertu na mapowanym urządzeniu musi zostać uruchomione zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="49b7b-114">A production order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="49b7b-115">Sygnał reprezentujący uszkodzenie części mapowanego urządzenia musi zostać wysłany do usługi IoT Hub o unikatowej nazwie właściwości.</span><span class="sxs-lookup"><span data-stu-id="49b7b-115">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="49b7b-116">Komunikat usługi IoT Hub musi zawierać właściwość znacznika czasu systemu UNIX w milisekundach.</span><span class="sxs-lookup"><span data-stu-id="49b7b-116">A Unix milliseconds timestamp property must be present in the IoT hub message.</span></span>

<span data-ttu-id="49b7b-117">Aby skonfigurować scenariusz, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="49b7b-117">To configure the scenario, follow these steps:</span></span>

1. <span data-ttu-id="49b7b-118">Zaloguj się do aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="49b7b-118">Log into Supply Chain Management.</span></span>
2. <span data-ttu-id="49b7b-119">Włącz flagę funkcji analizy Internetu rzeczy (IoT).</span><span class="sxs-lookup"><span data-stu-id="49b7b-119">Enable the IoT Intelligence feature flag.</span></span> <span data-ttu-id="49b7b-120">Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="49b7b-120">For more information, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
3. <span data-ttu-id="49b7b-121">Skonfiguruj metryki.</span><span class="sxs-lookup"><span data-stu-id="49b7b-121">Configure the metrics.</span></span> <span data-ttu-id="49b7b-122">Aby uzyskać więcej informacji, zobacz temat [.Jak skonfigurować metryki](iot-metrics-setup.md#configure-metrics).</span><span class="sxs-lookup"><span data-stu-id="49b7b-122">For more information, see [How to configure metrics](iot-metrics-setup.md#configure-metrics).</span></span>
4. <span data-ttu-id="49b7b-123">Przejdź do obszaru **Kontrola produkcji**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-123">Navigate to **Production control**.</span></span>
5. <span data-ttu-id="49b7b-124">Przejdź do pozycji **Ustawienia \> Analiza Internetu rzeczy (IoT) \> Zarządzanie scenariuszami**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-124">Navigate to **Setup \> IoT Intelligence \> Scenario management**.</span></span>
6. <span data-ttu-id="49b7b-125">Kliknij pozycję **Konfiguruj** na kafelku **przestoju sprzętu**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-125">Click **Configure** on the **Equipment downtime** tile.</span></span> <span data-ttu-id="49b7b-126">Kreator konfiguracji rozpoczyna się od strony **Definicja schematu czujnika sprzętu**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-126">The configuration wizard starts with the **Equipment sensor schema definition** page.</span></span> <span data-ttu-id="49b7b-127">Celem jest skonfigurowanie schematu w aplikacji Supply Chain Management w celu dopasowania go do formatu JSON wiadomości usługi IoT.</span><span class="sxs-lookup"><span data-stu-id="49b7b-127">The goal here is to setup the schema in Supply Chain Management to match the JSON format of the IoT messages.</span></span> <span data-ttu-id="49b7b-128">Można zdefiniować wiele schematów wiadomości.</span><span class="sxs-lookup"><span data-stu-id="49b7b-128">Multiple message schemas can be defined.</span></span> <span data-ttu-id="49b7b-129">Aby uzyskać więcej informacji, zapoznaj się z tematem [Formaty schematów wiadomości dla centrum IoT](iot-schema-format.md).</span><span class="sxs-lookup"><span data-stu-id="49b7b-129">For more information, see [Message schema formats for IoT Hub](iot-schema-format.md).</span></span> <span data-ttu-id="49b7b-130">W tym przykładzie ładunek wiadomości zawiera partię wiadomości o następującym formacie:</span><span class="sxs-lookup"><span data-stu-id="49b7b-130">In this example, the message payload contains a batch of messages with this format:</span></span>

    ```json
    {
        "timestamp": 1576016821614,
        "payload": [
            {
                "id": "IoTInt.Machine1225.PartOut",
                "timestamp": 1576016821614,
                "value": True
            },
            {
                "id": "IoTInt.Machine1226.PartOut",
                "timestamp": 1576016991616,
                "value": True
            }
        ]
    }
    ```

7. <span data-ttu-id="49b7b-131">Dodaj wiersz do tabeli.</span><span class="sxs-lookup"><span data-stu-id="49b7b-131">Add a row to the table.</span></span>

    1. <span data-ttu-id="49b7b-132">Ustaw **nazwę schematu** na **identyfikator**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-132">Set the **Schema name** to **ID**.</span></span>
    2. <span data-ttu-id="49b7b-133">Ustaw **ścieżkę schematu** na **/payload[\*]/id**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-133">Set the **Schema path** to **/payload[\*]/id**.</span></span>
    3. <span data-ttu-id="49b7b-134">Ustaw **opis** na **identyfikator wiadomości**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-134">Set the **Description** to **Message ID**.</span></span>

8. <span data-ttu-id="49b7b-135">Dodaj wiersz do tabeli.</span><span class="sxs-lookup"><span data-stu-id="49b7b-135">Add a row to the table.</span></span>

    1. <span data-ttu-id="49b7b-136">Ustaw **nazwę schematu** na **znacznik czasu**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-136">Set the **Schema name** to **Timestamp**.</span></span>
    2. <span data-ttu-id="49b7b-137">Ustaw **ścieżkę schematu** na **/payload[\*]/timestamp**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-137">Set the **Schema path** to **/payload[\*]/timestamp**.</span></span>
    3. <span data-ttu-id="49b7b-138">Ustaw **opis** na **znacznik czasu wiadomości**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-138">Set the **Description** to **Message timestamp**.</span></span>

9. <span data-ttu-id="49b7b-139">Dodaj wiersz do tabeli.</span><span class="sxs-lookup"><span data-stu-id="49b7b-139">Add a row to the table.</span></span>

    1. <span data-ttu-id="49b7b-140">Ustaw **nazwę schematu** na **wartość**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-140">Set the **Schema name** to **Value**.</span></span>
    2. <span data-ttu-id="49b7b-141">Ustaw **ścieżkę schematu** na **/payload[\*]/value**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-141">Set the **Schema path** to **/payload[\*]/value**.</span></span>
    3. <span data-ttu-id="49b7b-142">Ustaw **opis** na **wartość wiadomości**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-142">Set the **Description** to **Message value**.</span></span>

    <span data-ttu-id="49b7b-143">Nie trzeba definiować wszystkich właściwości w wiadomości, tylko te, których potrzebujesz.</span><span class="sxs-lookup"><span data-stu-id="49b7b-143">You don't need to define all the properties in the message, only the ones that you need.</span></span> <span data-ttu-id="49b7b-144">W tym przykładzie nie utworzono wiersza dla **głównego znacznika czasu**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-144">In this example, you did not create a row for **Root timestamp**.</span></span> <span data-ttu-id="49b7b-145">Ścieżką **głównego znacznika czasu** byłaby ścieżka **/timestamp**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-145">The path for **Root timestamp** would be **/timestamp**.</span></span>
  
10. <span data-ttu-id="49b7b-146">Kliknij pozycję **Dalej**, aby przejść do strony **Mapa schematów czujnika sprzętu**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-146">Click **Next** to go to the **Equipment sensor schema map** page.</span></span>
11. <span data-ttu-id="49b7b-147">W wierszu **identyfikatora zasobu sprzętu** ustaw **nazwę schematu** na **identyfikator**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-147">In the row for **Equipment resource ID** set the **Schema name** to **ID**.</span></span> <span data-ttu-id="49b7b-148">Prawidłowe wartości są wyświetlane w tabeli rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="49b7b-148">The valid values are displayed in a dropdown table.</span></span>
12. <span data-ttu-id="49b7b-149">W wierszu **czasu UTC** ustaw **nazwę schematu** na **znacznik czasu**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-149">In the row for **UTC time** set the **Schema name** to **Timestamp**.</span></span> <span data-ttu-id="49b7b-150">Prawidłowe wartości są wyświetlane w tabeli rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="49b7b-150">The valid values are displayed in a dropdown table.</span></span>
13. <span data-ttu-id="49b7b-151">W wierszu **sygnału wygenerowanego przez sprzęt** ustaw **nazwę schematu** na **wartość**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-151">In the row for **Part produced signal** set the **Schema name** to **Value**.</span></span> <span data-ttu-id="49b7b-152">Prawidłowe wartości są wyświetlane w tabeli rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="49b7b-152">The valid values are displayed in a dropdown table.</span></span>
14. <span data-ttu-id="49b7b-153">Kliknij pozycję **Dalej**, aby otworzyć stronę **Konfiguracja identyfikatora zasobu sprzętowego**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-153">Click **Next** for the **Equipment resource ID configuration** page.</span></span>
15. <span data-ttu-id="49b7b-154">W tym kroku wartości komunikatów centrum IoT są mapowane na zasoby aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="49b7b-154">In this step, you map the IoT Hub message values to the Supply Chain Management resources.</span></span>

    1. <span data-ttu-id="49b7b-155">W tabeli **Wartości danych sygnału** dodaj nowy wiersz i wprowadź ciąg **IoTInt.Machine1225.PartOut** w kolumnie **Wartość**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-155">In the **Signal Data Values** table, add a new row, and enter **IoTInt.Machine1225.PartOut** in the **Value** column.</span></span> <span data-ttu-id="49b7b-156">Wartość **IoTInt.Machine1225.PartOut** pochodzi z właściwości **id** notacji JSON w komunikacie centrum IoT.</span><span class="sxs-lookup"><span data-stu-id="49b7b-156">The value **IoTInt.Machine1225.PartOut** comes from the JSON **id** property in the IoT hub message.</span></span>
    2. <span data-ttu-id="49b7b-157">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-157">Click **Save**.</span></span>
    3. <span data-ttu-id="49b7b-158">W tabeli **Mapowanie rekordów biznesowych** kliknij pozycję **Nowe**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-158">In the **Business Record Mapping** table, click **New**.</span></span> <span data-ttu-id="49b7b-159">Domyślna wartość **typu rekordu biznesowego** jest wypełniana automatycznie i nie trzeba jej zmieniać.</span><span class="sxs-lookup"><span data-stu-id="49b7b-159">The default value for the **Business record type** is autopopulated, and you don't need to change it.</span></span>
    4. <span data-ttu-id="49b7b-160">W kolumnie **Rekord biznesowy** wybierz zasób urządzenia aplikacji Supply Chain Management, z którego jest wysyłana ta wartość sygnału.</span><span class="sxs-lookup"><span data-stu-id="49b7b-160">In the **Business record** column, select the Supple Chain Management machine resource this signal value is being sent from.</span></span>
    5. <span data-ttu-id="49b7b-161">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-161">Click **Save**.</span></span>
    6. <span data-ttu-id="49b7b-162">Powtórz te kroki, dodając nowe mapowanie rekordu biznesowego dla urządzenia **Machine1226**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-162">Repeat these steps, adding a new business record mapping for **Machine1226**.</span></span> <span data-ttu-id="49b7b-163">Można mapować wiele wartości danych sygnałów na pojedynczy rekord w aplikacji Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="49b7b-163">You can map multiple signal data values to a single record in Supply Chain Management.</span></span>

16. <span data-ttu-id="49b7b-164">Użyj kolumny **Wybrane**, aby wybrać urządzenia do przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="49b7b-164">Use the **Selected** column to choose which machines you want to process.</span></span> <span data-ttu-id="49b7b-165">Nie trzeba definiować wszystkich wartości sygnałów i nie trzeba wybierać wszystkich urządzeń.</span><span class="sxs-lookup"><span data-stu-id="49b7b-165">You do not have to define all signal values and you do not have to select all machines.</span></span>
17. <span data-ttu-id="49b7b-166">Kliknij pozycję **Dalej**, aby przejść na stronę **Konfiguracja sygnału wygenerowanego przez część**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-166">Click **Next** to go to the **Part produced signal configuration** page.</span></span>
18. <span data-ttu-id="49b7b-167">W tabeli **Wartości danych sygnału** dodaj wiersz i ustaw **wartość** na **Prawda**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-167">In the **Signal Data Values** table, add a row, and set **Value** to **True**.</span></span> <span data-ttu-id="49b7b-168">Wartość **Prawda** pochodzi z właściwości **value** notacji JSON w komunikacie centrum IoT.</span><span class="sxs-lookup"><span data-stu-id="49b7b-168">The value **True** comes from the JSON **value** property in the IoT hub message.</span></span> <span data-ttu-id="49b7b-169">Można dodać dowolną liczbę wartości potrzebnych w danym scenariuszu.</span><span class="sxs-lookup"><span data-stu-id="49b7b-169">You can add as many values as you need for your scenario.</span></span>
19. <span data-ttu-id="49b7b-170">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-170">Click **Save**.</span></span>
20. <span data-ttu-id="49b7b-171">Kliknij pozycję **Dalej**, aby przejść do strony **Próg przestoju sprzętu**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-171">Click **Next** to go to the **Equipment downtime threshold** page.</span></span> <span data-ttu-id="49b7b-172">Wymienione urządzenia to urządzenia uprzednio mapowane do wartości sygnałów.</span><span class="sxs-lookup"><span data-stu-id="49b7b-172">The machines listed are the machines previously mapped to signal values.</span></span> <span data-ttu-id="49b7b-173">W tym kroku zdefiniujesz próg określający, czy urządzenie nie działa.</span><span class="sxs-lookup"><span data-stu-id="49b7b-173">In this step, you define a threshold to determine if a machine is down.</span></span> <span data-ttu-id="49b7b-174">Jeśli na przykład wartość progu zostanie ustawiona na 10, aplikacja Supply Chain Management wygeneruje powiadomienie, jeśli przez 10 minut urządzenie nie wyśle komunikatu o niedziałającej części.</span><span class="sxs-lookup"><span data-stu-id="49b7b-174">For example, if you set the threshold to 10, Supply Chain Management generates a notification if there is no part out message from a machine for 10 minutes.</span></span>
21. <span data-ttu-id="49b7b-175">Kliknij pozycję **Dalej**, aby przejść na stronę **Włączanie scenariusza**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-175">Click **Next** to go to the **Enable scenario** page.</span></span> <span data-ttu-id="49b7b-176">Przełącz suwak, aby włączyć scenariusz.</span><span class="sxs-lookup"><span data-stu-id="49b7b-176">Toggle the slider to enable the scenario.</span></span>
22. <span data-ttu-id="49b7b-177">Kliknij przycisk **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-177">Click **Finish**.</span></span>

<span data-ttu-id="49b7b-178">Konfiguracja scenariusza została zakończona.</span><span class="sxs-lookup"><span data-stu-id="49b7b-178">The scenario setup is complete.</span></span> <span data-ttu-id="49b7b-179">W ramach analizy Internetu rzeczy (IoT) automatycznie rozpocznie się przetwarzanie komunikatów usługi IoT Hub.</span><span class="sxs-lookup"><span data-stu-id="49b7b-179">IoT Intelligence will automatically start processing the IoT Hub messages.</span></span>

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a><span data-ttu-id="49b7b-180">Konfigurowanie scenariusza **Jakość produktu** w aplikacji Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="49b7b-180">Configure the **Product quality** scenario in Supply Chain Management</span></span>

<span data-ttu-id="49b7b-181">Scenariusz **Jakość produktu** generuje powiadomienie, jeśli atrybut pozycji znajduje się poza określonym zakresem.</span><span class="sxs-lookup"><span data-stu-id="49b7b-181">The **Product quality** scenario generates a notification if an attribute of an item is outside a specified range.</span></span> <span data-ttu-id="49b7b-182">Na przykład czujnik może wysłać wagę każdej pozycji do usługi IoT Hub.</span><span class="sxs-lookup"><span data-stu-id="49b7b-182">For example, a sensor could send the weight of each item to IoT Hub.</span></span> <span data-ttu-id="49b7b-183">W aplikacji Supply Chain Management powiadomienie zostanie wygenerowane, jeśli pozycja była zbyt ciężka lub zbyt lekka.</span><span class="sxs-lookup"><span data-stu-id="49b7b-183">In Supply Chain Management, a notification would be generated if the item was too heavy or too light.</span></span>

<span data-ttu-id="49b7b-184">Scenariusz obejmuje następujące zależności:</span><span class="sxs-lookup"><span data-stu-id="49b7b-184">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="49b7b-185">Na mapowanym urządzeniu musi być uruchomione zlecenie produkcyjne, które powoduje tworzenie produktu z mapowanym atrybutem partii, aby alert został wyzwolony.</span><span class="sxs-lookup"><span data-stu-id="49b7b-185">A Production Order must be running on a mapped machine and producing a product with a mapped batch attribute for an alert to be triggered.</span></span>
+ <span data-ttu-id="49b7b-186">Sygnał reprezentujący atrybut partii musi zostać wysłany do usługi IoT Hub o unikatowej nazwie właściwości.</span><span class="sxs-lookup"><span data-stu-id="49b7b-186">A signal representing the batch attribute must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="49b7b-187">Komunikat usługi IoT Hub musi zawierać właściwość znacznika czasu systemu UNIX w milisekundach.</span><span class="sxs-lookup"><span data-stu-id="49b7b-187">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a><span data-ttu-id="49b7b-188">Konfigurowanie scenariusza **Opóźnienia produkcji** w aplikacji Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="49b7b-188">Configure the **Production delays** scenario in Supply Chain Management</span></span>

<span data-ttu-id="49b7b-189">Scenariusz **opóźnień produkcji** generuje powiadomienie, jeśli przepływność produkcji spadnie poniżej wartości progowej.</span><span class="sxs-lookup"><span data-stu-id="49b7b-189">The **Production delays** scenario generates a notification if the production throughput falls below a threshold value.</span></span> <span data-ttu-id="49b7b-190">W tym scenariuszu sygnał **PartOut** jest wysyłany do usługi IoT Hub dla każdej wyprodukowanej pozycji.</span><span class="sxs-lookup"><span data-stu-id="49b7b-190">In this scenario, a **PartOut** signal is sent to IoT Hub for each item produced.</span></span> <span data-ttu-id="49b7b-191">W aplikacji Supply Chain Management opóźnienie zamówienia jest obliczane na podstawie czasu, przez jaki jest planowane działanie zlecenia produkcyjnego, liczby pozycji do wyprodukowania, czasu trwania zadania oraz liczby odebranych sygnałów **PartOut**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-191">In Supply Chain Management, the order delay is calculated based on how long the production order is scheduled to run, how many items should be produced, how long the job has been running, and how many **PartOut** signals are received.</span></span> <span data-ttu-id="49b7b-192">Powiadomienie o opóźnieniu zostanie wygenerowane, jeśli liczba sygnałów **PartOut** dla zadania spadnie poniżej wartości progowej oczekiwanej wartości.</span><span class="sxs-lookup"><span data-stu-id="49b7b-192">A delay notification would be generated if the number of the **PartOut** signals for the job falls below the threshold value of the expected value.</span></span>

<span data-ttu-id="49b7b-193">Scenariusz obejmuje następujące zależności:</span><span class="sxs-lookup"><span data-stu-id="49b7b-193">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="49b7b-194">W celu wyzwolenia alertu na mapowanym urządzeniu musi zostać uruchomione zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="49b7b-194">A Production Order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="49b7b-195">Sygnał reprezentujący uszkodzenie części mapowanego urządzenia musi zostać wysłany do usługi IoT Hub o unikatowej nazwie właściwości.</span><span class="sxs-lookup"><span data-stu-id="49b7b-195">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="49b7b-196">Komunikat usługi IoT Hub musi zawierać właściwość znacznika czasu systemu UNIX w milisekundach.</span><span class="sxs-lookup"><span data-stu-id="49b7b-196">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="how-to-disable-a-scenario"></a><span data-ttu-id="49b7b-197">Jak wyłączyć scenariusz</span><span class="sxs-lookup"><span data-stu-id="49b7b-197">How to disable a scenario</span></span>

<span data-ttu-id="49b7b-198">Aby wyłączyć scenariusz, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="49b7b-198">To disable a scenario, follow these steps:</span></span>

1. <span data-ttu-id="49b7b-199">W aplikacji Supply Chain Management przejdź do pozycji **Kontrola produkcji \> Ustawienia \> Analiza Internetu rzeczy (IoT) \> Zarządzanie scenariuszami**.</span><span class="sxs-lookup"><span data-stu-id="49b7b-199">In Supply Chain Management, navigate to **Production control \> Setup \> IoT Intelligence \> Scenario management**.</span></span>
2. <span data-ttu-id="49b7b-200">Kliknij pozycję **Konfiguruj** w scenariuszu.</span><span class="sxs-lookup"><span data-stu-id="49b7b-200">Click **Configure** on the scenario.</span></span>
3. <span data-ttu-id="49b7b-201">Kliknij pozycję **Dalej**, aby przejść do ostatniej karty kreatora.</span><span class="sxs-lookup"><span data-stu-id="49b7b-201">Click **Next** to get to the last wizard tab.</span></span>
4. <span data-ttu-id="49b7b-202">Przełącz suwak, aby wyłączyć scenariusz.</span><span class="sxs-lookup"><span data-stu-id="49b7b-202">Toggle the slider to disable the scenario.</span></span>
