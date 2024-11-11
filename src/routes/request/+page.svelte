<script>
    let disasterType = '';
    let fullName = '';
    let contactNumber = '';
    let location = '';
    let nearestLandmark = '';
    let numberOfPeople = '';
    let description = '';
    let isConsentGiven = false;

    let injuryDetails = '';
    let immediateNeeds = '';
    let structuralDamage = '';
    let trappedPeople = false;

    const handleSubmit = () => {
        if (!fullName || !contactNumber || !location || !disasterType || !description || !isConsentGiven) {
            alert("Please fill in all required fields and consent to share information.");
            return;
        }

        console.log("Disaster Request Data:", {
            fullName,
            contactNumber,
            location,
            nearestLandmark,
            disasterType,
            description,
            numberOfPeople,
            injuryDetails,
            immediateNeeds,
            structuralDamage,
            trappedPeople,
            isConsentGiven
        });

        alert("Your request has been submitted successfully!");
    };
</script>

<style>
    @import './request.css';
</style>
<div class="navbar">
    <h1>Request</h1>
</div>
<div class="container">
    <form on:submit|preventDefault={handleSubmit}>
        <!-- General Information -->
        <div class="form-section">
            <label for="fullName">Full Name *</label>
            <input type="text" id="fullName" bind:value={fullName} required />

            <label for="contactNumber">Contact Number *</label>
            <input type="text" id="contactNumber" bind:value={contactNumber} required />

            <label for="location">Location *</label>
            <input type="text" id="location" bind:value={location} required />

            <label for="nearestLandmark">Nearest Landmark (Optional)</label>
            <input type="text" id="nearestLandmark" bind:value={nearestLandmark} />

            <label for="disasterType">Type of Disaster *</label>
            <select id="disasterType" bind:value={disasterType} required>
                <option value="">Select Disaster Type</option>
                <option value="flood">Flood</option>
                <option value="earthquake">Earthquake</option>
                <option value="typhoon">Typhoon</option>
                <option value="landslide">Landslide</option>
                <option value="fire">Fire</option>
                <option value="other">Other</option>
            </select>

            <label for="description">Description of the Situation *</label>
            <textarea id="description" bind:value={description} required></textarea>
        </div>

        <!-- Additional Details for Disaster Readiness -->
        <div class="form-section">
            <label for="numberOfPeople">Number of People Affected</label>
            <input type="number" id="numberOfPeople" bind:value={numberOfPeople} min="1" />

            <label for="injuryDetails">Injuries or Medical Needs</label>
            <textarea id="injuryDetails" bind:value={injuryDetails}></textarea>

            <label for="immediateNeeds">Immediate Needs (e.g., food, water, shelter)</label>
            <textarea id="immediateNeeds" bind:value={immediateNeeds}></textarea>

            <label for="structuralDamage">Description of Structural Damage</label>
            <textarea id="structuralDamage" bind:value={structuralDamage}></textarea>

            <label><input type="checkbox" bind:checked={trappedPeople} /> Are there any trapped individuals?</label>
        </div>

        <!-- Consent Checkbox -->
        <div class="form-section">
            <label><input type="checkbox" bind:checked={isConsentGiven} /> I consent to share this information with emergency responders *</label>
        </div>

        <!-- Submit Button -->
        <button type="submit">Submit Request</button>
    </form>
</div>

<footer class="footer">
    <a class="home-n" href="/home">
        <svg class="w-6 h-6" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="white" viewBox="0 0 24 24">
            <path fill-rule="evenodd" d="M11.293 3.293a1 1 0 0 1 1.414 0l6 6 2 2a1 1 0 0 1-1.414 1.414L19 12.414V19a2 2 0 0 1-2 2h-3a1 1 0 0 1-1-1v-3h-2v3a1 1 0 0 1-1 1H7a2 2 0 0 1-2-2v-6.586l-.293.293a1 1 0 0 1-1.414-1.414l2-2 6-6Z" clip-rule="evenodd"/>
        </svg>            
        Home
    </a>
    <a class="request" href="/request">
        <svg class="w-6 h-6" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="white" viewBox="0 0 24 24">
            <path fill-rule="evenodd" d="M12 4a4 4 0 1 0 0 8 4 4 0 0 0 0-8Zm-2 9a4 4 0 0 0-4 4v1a2 2 0 0 0 2 2h8a2 2 0 0 0 2-2v-1a4 4 0 0 0-4-4h-4Z" clip-rule="evenodd"/>
        </svg>           
        Request
    </a>
    <a class="status-n" href="/status">
        <svg class="w-6 h-6 text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
            <path stroke="white" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m16 10 3-3m0 0-3-3m3 3H5v3m3 4-3 3m0 0 3 3m-3-3h14v-3"/>
        </svg>
        Status
    </a>
    <a class="hotline-n" href="/hotlines">
        <svg class="w-6 h-6 text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
            <path stroke="white" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 9H5a1 1 0 0 0-1 1v4a1 1 0 0 0 1 1h6m0-6v6m0-6 5.419-3.87A1 1 0 0 1 18 5.942v12.114a1 1 0 0 1-1.581.814L11 15m7 0a3 3 0 0 0 0-6M6 15h3v5H6v-5Z"/>
        </svg>
        Hotlines
    </a>
</footer>