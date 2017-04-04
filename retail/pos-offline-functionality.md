---
title: "Funkcjonalność offline punktu sprzedaży"
description: "Ten artykuł zawiera informacje o trybie offline modułu Retail Modern POS, w którym urządzenia w punkach sprzedaży automatycznie przełączają się z bazy danych kanału na bazę danych trybu offline w przypadku niedostępności serwera obsługi sprzedaży detalicznej. Artykuł zawiera również ogólne informacje o konfigurowaniu trybu offline oraz objaśnienie synchronizacji danych wykonywanej między bazą danych offline a bazą danych kanału."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27041
ms.assetid: 20b51874-8912-40cf-9296-864df707315a
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ef4d20b3302e4a420c7013b77a57ebdfa99fe6a3
ms.lasthandoff: 03/31/2017


---

# <a name="pos-offline-functionality"></a>Funkcjonalność offline punktu sprzedaży

Ten artykuł zawiera informacje o trybie offline modułu Retail Modern POS, w którym urządzenia w punkach sprzedaży automatycznie przełączają się z bazy danych kanału na bazę danych trybu offline w przypadku niedostępności serwera obsługi sprzedaży detalicznej. Artykuł zawiera również ogólne informacje o konfigurowaniu trybu offline oraz objaśnienie synchronizacji danych wykonywanej między bazą danych offline a bazą danych kanału.

<a name="overview"></a>Przegląd
--------

W nowoczesnych Retail POS punktu sprzedaży (POS) urządzenie przechodzi w tryb offline w każdym przypadku, gdy nie jest dostępny serwer sprzedaży detalicznej. W związku z tym w przypadku utraty połączenia z serwerem sieci sprzedaży program Retail POS nowoczesnych automatycznie przełącza do bazy danych trybu offline. Podczas transakcji sprzedaży jeśli żądanie danych nie powiodło się w skonfigurowanym w profilu trybu offline limicie czasu, Retail Modern POS automatycznie przełącza się na bazę danych trybu offline i kontynuuje transakcję sprzedaży. Gdy urządzenie punktu sprzedaży jest w trybie offline, Retail Modern POS podejmuje próby połączenia z serwerem sieci sprzedaży po czasie oczekiwania ustawionym w profilu trybu offline. Próba ponownego połączenia jest wykonywana tylko na początku transakcji.

### <a name="determining-the-connection-mode-of-retail-modern-pos"></a>Określanie trybu połączenia Retail Modern POS

Nagłówek stanu w programie Retail Modern POS wskazuje bieżący stan połączenia, a okno **Stan połączenia** pokazuje stan ostatniej próby synchronizacji z bazą danych trybu offline. [![Connection status](./media/status.png)](./media/status.png)

### <a name="creating-a-button-to-manually-switch-between-online-and-offline-modes"></a>Tworzenie przycisku do ręcznego przełączania między trybem offline i online

Do Retail Modern POS można dodać przycisk automatycznego przełączania między trybem online i offline. Utwórz przycisk dla operacji punktu sprzedaży **917 — stan połączenia bazy danych**. Ten przycisk ma nazwę **Rozłącz** lub **Połącz** odpowiednio gdy Retail Modern POS jest połączony z serwerem sieci sprzedaży lub gdy jest rozłączony. Za pomocą tego przycisku można wyświetlić stan połączenia oraz rozłączyć się lub połączyć z serwerem sieci sprzedaży. [![Odłącz przycisku w programie Retail POS nowoczesny](./media/details-1024x537.png)](./media/details.png)

## <a name="setup"></a>Ustawienia
Aby włączyć obsługę trybu offline dla urządzenia POS (rejestr), należy ustawić **obsługi w trybie offline** opcji w celu **tak** na **zarejestrować** strony. Nowy obiekt bazy danych kanału jest tworzony i dodawany do grupy danych kanału w sklepie. Następnie uruchom wszystkie wymagane harmonogramy dystrybucji do generowania pakietów danych dla bazy danych offline. Następnie zainstaluj wersji offline nowoczesny punkt sprzedaży. Proces instalacji utworzy bazę danych trybu offline. Microsoft SQL Server 2014 Express zainstalować dodatkowo, jeśli jest to wymagane. Synchronizacja danych offline rozpoczyna się od pierwszego logowania do Retail Modern POS.

## <a name="data-synchronization"></a>Synchronizacja danych
Do wysyłania danych głównych do bazy danych trybu offline służy Transfer danych w sieci sprzedaży. Domyślnie po uruchomieniu harmonogramu dystrybucji zmiany danych są wysyłane do bazy danych kanału i bazy danych trybu offline. Retail Modern POS zawiera bibliotekę synchronizacji asynchronicznej, która pobiera wszelkie dostępne pakiety danych i wstawia je do bazy offline. W razie utworzenia transakcji offline Retail Modern POS przesyła je do serwera sieci sprzedaży, tak aby można było je wstawić do bazy danych kanału. Synchronizacja danych trybu offline może wystąpić tylko wtedy, gdy działa Retail Modern POS. [![Offline synchronization](./media/offline-sync-1024x521.png)](./media/offline-sync.png)


