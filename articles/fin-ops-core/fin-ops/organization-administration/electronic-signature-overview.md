---
title: Omówienie podpisów elektronicznych
description: Ten artykuł zawiera omówienie podpisów elektronicznych, a także opis sposobu ich używania.
author: maertenm
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SIGParameters, SIGProcSetup, SIGReasonCode
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 13611
ms.assetid: 98dc6b79-1895-45d8-9dd1-2c8a351b58af
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d1d8952324bb16bcfa6a8b42fc4f157edb75cf1
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811331"
---
# <a name="electronic-signatures-overview"></a><span data-ttu-id="14051-103">Omówienie podpisów elektronicznych</span><span class="sxs-lookup"><span data-stu-id="14051-103">Electronic signatures overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="14051-104">Ten artykuł zawiera omówienie podpisów elektronicznych, a także opis sposobu ich używania.</span><span class="sxs-lookup"><span data-stu-id="14051-104">This article provides an overview of electronic signatures and describes how they can be used.</span></span>

## <a name="what-is-an-electronic-signature"></a><span data-ttu-id="14051-105">Co to jest podpis elektroniczny?</span><span class="sxs-lookup"><span data-stu-id="14051-105">What is an electronic signature?</span></span>

<span data-ttu-id="14051-106">Podpis elektroniczny potwierdza tożsamość osoby, która ma rozpocząć lub zatwierdzić jakiś proces obliczeniowy.</span><span class="sxs-lookup"><span data-stu-id="14051-106">An electronic signature confirms the identity of a person who is about to start or approve a computing process.</span></span> <span data-ttu-id="14051-107">W przypadku niektórych branż podpis elektroniczny jest tak samo prawnie wiążący jak podpis odręczny.</span><span class="sxs-lookup"><span data-stu-id="14051-107">In some industries, an electronic signature is as legally binding as a handwritten signature.</span></span>

<span data-ttu-id="14051-108">Podpisy elektroniczne są wymagane przepisami w przypadku kilku branż regulowanych, takich jak przemysł farmaceutyczny, spożywczy oraz lotniczy i obronny.</span><span class="sxs-lookup"><span data-stu-id="14051-108">Electronic signatures are a regulations compliance requirement for several regulated industries, such as pharmaceuticals, food and beverage, and aerospace and defense.</span></span> <span data-ttu-id="14051-109">Wymagają ich również przepisy 21 CFR część 11 wydane przez amerykańską Agencję ds. Żywności i Leków (FDA).</span><span class="sxs-lookup"><span data-stu-id="14051-109">They are also required for compliance with regulations in 21 CFR Part 11 that was issued by the Food and Drug Administration (FDA) in the United States.</span></span>

> [!NOTE]
> <span data-ttu-id="14051-110">Sam podpis elektroniczny nie jest tym samym, co podpis cyfrowy.</span><span class="sxs-lookup"><span data-stu-id="14051-110">An electronic signature by itself isn't the same as a digital signature.</span></span> <span data-ttu-id="14051-111">Podpis elektroniczny jest po prostu substytutem podpisu odręcznego, podczas gdy podpis cyfrowy stanowi dodatkowy środek zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="14051-111">An electronic signature is just a substitute for a handwritten signature, whereas a digital signature provides additional security measures.</span></span> <span data-ttu-id="14051-112">Podpis cyfrowy pomaga w ustaleniu, czy inny użytkownik lub proces nie naruszył danych.</span><span class="sxs-lookup"><span data-stu-id="14051-112">A digital signature can help identify whether another user or process has tampered with the data.</span></span> <span data-ttu-id="14051-113">Podpis cyfrowy może być również weryfikowany i ta weryfikacja nie może zostać zakwestionowana przez właściciela certyfikatu użytego do podpisania danych.</span><span class="sxs-lookup"><span data-stu-id="14051-113">A digital signature can also be verified, and this verification can't be refuted by the owner of the certificate that was used to sign the data.</span></span> <span data-ttu-id="14051-114">Jak opisano poniżej, podpisy elektroniczne mają wbudowaną funkcjonalność podpisu cyfrowego.</span><span class="sxs-lookup"><span data-stu-id="14051-114">As described below, electronic signatures have built-in digital signature functionality.</span></span>

## <a name="electronic-signatures"></a><span data-ttu-id="14051-115">Podpisy elektroniczne</span><span class="sxs-lookup"><span data-stu-id="14051-115">Electronic signatures</span></span>

<span data-ttu-id="14051-116">Można używać podpisów elektronicznych w przypadku procesów biznesowych o podstawowym znaczeniu.</span><span class="sxs-lookup"><span data-stu-id="14051-116">You can use electronic signatures for critical business processes.</span></span> <span data-ttu-id="14051-117">Niektóre procesy mają wbudowane możliwości podpisu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="14051-117">Some processes have built-in electronic signature capabilities.</span></span> <span data-ttu-id="14051-118">Można również tworzyć niestandardowe wymagania dotyczące podpisu cyfrowego dla dowolnej tabeli lub pola bazy danych.</span><span class="sxs-lookup"><span data-stu-id="14051-118">You can also create custom signature requirements for any database table and field.</span></span>

<span data-ttu-id="14051-119">Podpisy elektroniczne mają wbudowaną funkcjonalność podpisu cyfrowego.</span><span class="sxs-lookup"><span data-stu-id="14051-119">Electronic signatures have built-in digital signature functionality.</span></span> <span data-ttu-id="14051-120">Każdy użytkownik, który podpisuje dokumenty, musi uzyskać prawidłowy certyfikat kryptograficzny.</span><span class="sxs-lookup"><span data-stu-id="14051-120">Every user who signs documents must obtain a valid cryptographic certificate.</span></span> <span data-ttu-id="14051-121">Podczas podpisywania dokumentu sprawdzana jest poprawność klucza prywatnego skojarzonego z tym certyfikatem.</span><span class="sxs-lookup"><span data-stu-id="14051-121">When a document is signed, the private key that is associated with that certificate is validated.</span></span> <span data-ttu-id="14051-122">Informacje dotyczące podpisów elektronicznych są rejestrowane w dzienniku inspekcji.</span><span class="sxs-lookup"><span data-stu-id="14051-122">Electronic signature information is recorded in a log to provide an audit trail.</span></span> <span data-ttu-id="14051-123">Aby skonfigurować podpisy elektroniczne, zobacz [Konfigurowanie podpisów elektronicznych](tasks/set-up-electronic-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="14051-123">To set up electronic signatures, see [Set up electronic signatures](tasks/set-up-electronic-signatures.md).</span></span>

## <a name="users-who-require-access-to-electronic-signatures"></a><span data-ttu-id="14051-124">Użytkownicy, którzy potrzebują dostępu do podpisów elektronicznych</span><span class="sxs-lookup"><span data-stu-id="14051-124">Users who require access to electronic signatures</span></span>

<span data-ttu-id="14051-125">Trzy rodzaje użytkowników zwykle wymagają dostępu zabezpieczeń do podpisów elektronicznych: administratorzy podpisów elektronicznych, osoby podpisujące i audytorzy podpisów elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="14051-125">Three kinds of users typically require security access to electronic signatures: electronic signature administrators, signers, and electronic signature auditors.</span></span>

### <a name="electronic-signature-administrator"></a><span data-ttu-id="14051-126">Administrator podpisów elektronicznych</span><span class="sxs-lookup"><span data-stu-id="14051-126">Electronic signature administrator</span></span>

<span data-ttu-id="14051-127">Administrator podpisów elektronicznych konfiguruje wymagania dotyczące podpisów, parametry ogólne i osoby zatwierdzające, a ponadto otrzymuje alerty w przypadku, gdy nie można sprawdzić poprawności podpisu.</span><span class="sxs-lookup"><span data-stu-id="14051-127">The electronic signature administrator sets up signature requirements, general parameters, and approvers, and receives alerts when signatures can't be verified.</span></span> <span data-ttu-id="14051-128">Domyślnie każdy użytkownik, który należy do roli zabezpieczeń **Menedżer ds. informatyki** ma uprawnienie do zarządzania podpisami elektronicznymi.</span><span class="sxs-lookup"><span data-stu-id="14051-128">By default, a user who belongs to the **Information technology manager** security role has permission to administer electronic signatures.</span></span>

### <a name="signer"></a><span data-ttu-id="14051-129">Osoba podpisująca</span><span class="sxs-lookup"><span data-stu-id="14051-129">Signer</span></span>

<span data-ttu-id="14051-130">Osoba podpisująca składa podpisy elektroniczne w przypadku dokumentów i procesów wymagających podpisów.</span><span class="sxs-lookup"><span data-stu-id="14051-130">A signer provides electronic signatures for documents and processes that require signatures.</span></span> <span data-ttu-id="14051-131">Domyślnie każdy użytkownik, który należy do roli zabezpieczeń **Użytkownik systemu**, ma uprawnienie do korzystania z elektronicznych podpisów dokumentów.</span><span class="sxs-lookup"><span data-stu-id="14051-131">By default, a user who belongs to the **System user** security role has permission to sign documents electronically.</span></span>

> [!NOTE]
> <span data-ttu-id="14051-132">Osoba podpisująca może wymagać dodatkowych uprawnień, aby uzyskać dostęp do danych związanych z podpisywanym dokumentem lub procesem.</span><span class="sxs-lookup"><span data-stu-id="14051-132">The signer might require additional permissions before access is granted to data that is related to the document or process that is being signed.</span></span> <span data-ttu-id="14051-133">Użytkownik, który wprowadza zmiany w danych i musi je następnie podpisać, musi mieć uprawnienie do modyfikacji danych.</span><span class="sxs-lookup"><span data-stu-id="14051-133">A user who changes data and must then sign for those changes must have permission to change the data.</span></span> <span data-ttu-id="14051-134">Użytkownik, który ma podpisywać zmiany w imieniu innego użytkownika, może nie wymagać dostępu do danych.</span><span class="sxs-lookup"><span data-stu-id="14051-134">A user who signs on behalf of another user might not require access to the data.</span></span> <span data-ttu-id="14051-135">Przykładem tego rodzaju użytkownika jest inspektor, który podpisuje zmiany pracownika.</span><span class="sxs-lookup"><span data-stu-id="14051-135">An example of this kind of user is a supervisor who signs for an employee's changes.</span></span>

### <a name="electronic-signature-auditor"></a><span data-ttu-id="14051-136">Audytorów podpisów elektronicznych</span><span class="sxs-lookup"><span data-stu-id="14051-136">Electronic signature auditor</span></span>

<span data-ttu-id="14051-137">Audytor podpisów elektronicznych przegląda dziennik bazy danych oraz dziennik przeglądu podpisów, który jest dostępny z dziennika bazy danych.</span><span class="sxs-lookup"><span data-stu-id="14051-137">The electronic signature auditor reviews the database log and the signature review log that is available from the database log.</span></span> <span data-ttu-id="14051-138">Domyślnie każdy użytkownik, który należy do roli zabezpieczeń **Menedżer ds. informatyki** ma uprawnienie do inspekcji podpisów elektronicznych.</span><span class="sxs-lookup"><span data-stu-id="14051-138">By default, a user who belongs to the **Information technology manager** security role has permission to audit electronic signatures.</span></span>

<span data-ttu-id="14051-139">Jeśli używasz innych ról niż **Menedżer ds. informatyki**, upewnij się, że przypisano roli następujące uprawnienia:</span><span class="sxs-lookup"><span data-stu-id="14051-139">If you use a role other than **Information technology manager**, make sure that the role is assigned the following privileges:</span></span>

- <span data-ttu-id="14051-140">Przeglądanie błędów podpisu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="14051-140">View electronic signature failures</span></span>
- <span data-ttu-id="14051-141">Przeglądanie dziennika bazy danych</span><span class="sxs-lookup"><span data-stu-id="14051-141">View database log</span></span>

## <a name="signing-documents-electronically"></a><span data-ttu-id="14051-142">Elektroniczne podpisywanie dokumentów</span><span class="sxs-lookup"><span data-stu-id="14051-142">Signing documents electronically</span></span>

### <a name="get-a-certificate"></a><span data-ttu-id="14051-143">Uzyskiwanie certyfikatu</span><span class="sxs-lookup"><span data-stu-id="14051-143">Get a certificate</span></span>

<span data-ttu-id="14051-144">Aby móc elektronicznie podpisywać dokumenty, musisz zażądać certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="14051-144">Before you sign documents electronically, you must request a certificate.</span></span>

> [!NOTE]
> <span data-ttu-id="14051-145">Funkcje Microsoft SQL Server są używane do tworzenia certyfikatów i włączania funkcjonalności podpisu cyfrowego.</span><span class="sxs-lookup"><span data-stu-id="14051-145">Microsoft SQL Server features are used to create certificates and enable electronic signing.</span></span> <span data-ttu-id="14051-146">Nie jest wymagana żadna dodatkowa infrastruktura certyfikatów czy kluczy publicznych (PKI).</span><span class="sxs-lookup"><span data-stu-id="14051-146">No additional certificate or public key infrastructure (PKI) is required.</span></span>

<span data-ttu-id="14051-147">Gdy zażądasz certyfikatu, są dla Ciebie tworzone klucze publiczny i prywatny.</span><span class="sxs-lookup"><span data-stu-id="14051-147">When you request a certificate, a public key and a private key are created for you.</span></span> <span data-ttu-id="14051-148">Klucz prywatny jest zaszyfrowany przy użyciu hasła znanego tylko Tobie.</span><span class="sxs-lookup"><span data-stu-id="14051-148">The private key is encrypted by using a password that is known only to you.</span></span> <span data-ttu-id="14051-149">Gdy podpisujesz dokument elektronicznie, Twoja tożsamość jest weryfikowana podczas wprowadzenia hasła.</span><span class="sxs-lookup"><span data-stu-id="14051-149">When you sign a document electronically, your identity is verified when you enter the password.</span></span>

<span data-ttu-id="14051-150">Aby zażądać certyfikatu, na stronie **Opcje** na karcie **Konta** kliknij przycisk **Pobierz certyfikat**.</span><span class="sxs-lookup"><span data-stu-id="14051-150">To request a certificate, on the **Options** page, on the **Accounts** tab, click **Get certificate**.</span></span>

<span data-ttu-id="14051-151">Musisz wprowadzić i potwierdzić hasło, którego będziesz używać do składania podpisu.</span><span class="sxs-lookup"><span data-stu-id="14051-151">You must enter and confirm the password that you will use for signing.</span></span> <span data-ttu-id="14051-152">To hasło służy do ochrony klucza prywatnego i upoważnia do użycia certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="14051-152">The password is used to protect your private key and authorize the use of your certificate.</span></span> <span data-ttu-id="14051-153">Nie jest ono przechowywane w bazie danych i nie jest dostępne nikomu innemu, w tym również administratorowi.</span><span class="sxs-lookup"><span data-stu-id="14051-153">This password isn't stored in the database, and it isn't available to anyone else, not even to the administrator.</span></span>

<span data-ttu-id="14051-154">W razie zapomnienia hasła połączonego z certyfikatem należy zresetować certyfikat.</span><span class="sxs-lookup"><span data-stu-id="14051-154">If you forget the password that is connected with your certificate, that certificate must be reset.</span></span> <span data-ttu-id="14051-155">Zresetowanie certyfikatu nie wpływa na dokumenty podpisane przy użyciu poprzedniego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="14051-155">If you reset the certificate, you don't affect documents that you signed by using the previous certificate.</span></span> <span data-ttu-id="14051-156">Aby zresetować certyfikat, na stronie **Opcje** kliknij przycisk **Resetuj certyfikat**.</span><span class="sxs-lookup"><span data-stu-id="14051-156">To reset the certificate, on the **Options** page, click **Reset certificate**.</span></span>

### <a name="sign-a-document-electronically"></a><span data-ttu-id="14051-157">Elektroniczne podpisywanie dokumentu</span><span class="sxs-lookup"><span data-stu-id="14051-157">Sign a document electronically</span></span>

<span data-ttu-id="14051-158">W przypadku dokonania zmiany wymagającej podpisu elektronicznego wyświetlana jest strona **Podpisz dokument**.</span><span class="sxs-lookup"><span data-stu-id="14051-158">The **Sign document** page is displayed when you make a change that requires an electronic signature.</span></span>

1. <span data-ttu-id="14051-159">Na stronie **Podpisz dokument** kliknij kartę **Dokument**, aby przejrzeć zmiany dokonane w dokumencie.</span><span class="sxs-lookup"><span data-stu-id="14051-159">On the **Sign document** page, click the **Document** tab to review the changes to the document.</span></span>
2. <span data-ttu-id="14051-160">Na karcie **Podpis** wybierz kod przyczyny.</span><span class="sxs-lookup"><span data-stu-id="14051-160">On the **Signature** tab, select a reason code.</span></span>
3. <span data-ttu-id="14051-161">Wprowadź komentarz, jeśli jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="14051-161">Enter a comment, if a comment is required.</span></span>
4. <span data-ttu-id="14051-162">Jeśli Twój identyfikator użytkownika nie jest wyświetlany w polu **Osoba podpisująca**, wybierz go z listy.</span><span class="sxs-lookup"><span data-stu-id="14051-162">If your user ID doesn't appear in the **Signer** field, select it in the list.</span></span>
5. <span data-ttu-id="14051-163">Wprowadź swoją lokalizację, jeśli ta informacja jest wymagana.</span><span class="sxs-lookup"><span data-stu-id="14051-163">Enter your location, if this information is required.</span></span>
6. <span data-ttu-id="14051-164">Kliknij przycisk **OK**</span><span class="sxs-lookup"><span data-stu-id="14051-164">Click **OK**.</span></span>

### <a name="sign-for-another-users-changes"></a><span data-ttu-id="14051-165">Podpisywanie zmian dokonanych przez innego użytkownika</span><span class="sxs-lookup"><span data-stu-id="14051-165">Sign for another user's changes</span></span>

<span data-ttu-id="14051-166">Czasami możesz chcieć podpisać zmiany dokonane przez innego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="14051-166">Occasionally, you might want a user to sign for another user's changes.</span></span> <span data-ttu-id="14051-167">Na przykład przełożony może mieć obowiązek podpisywania zmian wprowadzonych przez pracownika na liście składowej (BOM).</span><span class="sxs-lookup"><span data-stu-id="14051-167">For example, a supervisor might be required to sign for changes that an employee makes to a bill of materials (BOM).</span></span> <span data-ttu-id="14051-168">Niniejszej procedury należy użyć, aby wyznaczyć użytkownika na osobę podpisującą dla innego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="14051-168">Use this procedure to designate a user as a signer for another user.</span></span>

> [!NOTE]
> <span data-ttu-id="14051-169">Jeśli użytkownik podpisuje zmianę dokonaną przez innego użytkownika, podpis musi zostać złożony na stacji roboczej użytkownika, który dokonał zmiany.</span><span class="sxs-lookup"><span data-stu-id="14051-169">When one user signs for another user's change, the signature must be provided at the workstation of the user who made the change.</span></span> <span data-ttu-id="14051-170">Użytkownik ten będzie miał możliwości zapisania zmiany dopiero po złożeniu podpisu.</span><span class="sxs-lookup"><span data-stu-id="14051-170">The user can't save the change until the signature has been provided.</span></span>

<span data-ttu-id="14051-171">Aby wyznaczyć osoby zatwierdzające, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="14051-171">To designate approvers, follow these steps.</span></span>

1. <span data-ttu-id="14051-172">Na stronie **Opcje** na karcie **Konta** kliknij opcję **Wyznacz osobę zatwierdzającą**.</span><span class="sxs-lookup"><span data-stu-id="14051-172">On the **Options** page, on the **Accounts** tab, click **Designate approver**.</span></span>
2. <span data-ttu-id="14051-173">W polu **Identyfikator użytkownika osoby zatwierdzającej** wybierz identyfikator użytkownika, który ma podpisywać zmiany dokonane przez innego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="14051-173">In the **Approver user ID** field, select the ID of the user who must sign for another user's changes.</span></span>
3. <span data-ttu-id="14051-174">W polu **Identyfikator użytkownika osoby potrzebującej podpisu** wybierz identyfikator użytkownika, którego zmiany mają być podpisywane.</span><span class="sxs-lookup"><span data-stu-id="14051-174">In the **Sign for user ID** field, select the ID of the user whose changes must be signed for.</span></span>
