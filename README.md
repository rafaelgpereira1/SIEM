<h1>SIEM with Azure Sentinel</h1>

<h2>Overview of the Process</h2>
<ul>
  <li>
    Configured Azure Sentinel (Microsoft’s cloud SIEM) to visualize global RDP brute force attacks on an interactive world map.
  </li>
  <li>
    Created a custom PowerShell script to gather metadata from Windows Event Viewer, forwarding data to a third-party API for geolocation enrichment.
  </li>
  <li>
    Utilized Azure Log Analytics to ingest customized logs containing geolocation details (latitude, longitude, state/province, country).
  </li>
  <li>
    Set up custom fields in Azure Sentinel to map the location data, enabling insightful dashboards and threat analysis.
  </li>
</ul>

<h3>1. Configure Azure Sentinel Workbook</h3>
<ul>
  <li>
    <strong>Set Up Sentinel</strong><br/>
    <ul>
      <li>Enable Azure Sentinel in your Azure environment and link it to a dedicated Log Analytics workspace.</li>
      <li>Access the Sentinel portal to begin configuring data sources and analytics rules.</li>
    </ul>
  </li>
  <li>
    <strong>Create or Customize a Workbook</strong><br/>
    <ul>
      <li>Open the “Workbooks” section in Azure Sentinel and choose a pre-built template or start from scratch.</li>
      <li>Design the layout for displaying global attack data, integrating map visuals.</li>
    </ul>
  </li>
</ul>

<h3>2. Implement PowerShell for Geolocation Data</h3>
<ul>
  <li>
    <strong>Extract Metadata from Windows Event Viewer</strong><br/>
    <ul>
      <li>Develop a PowerShell script that parses event logs—particularly those indicating RDP brute force attempts.</li>
      <li>Gather relevant fields (e.g., IP addresses, timestamps) required for geolocation lookups.</li>
    </ul>
  </li>
  <li>
    <strong>Forward Data to Third-Party API</strong><br/>
    <ul>
      <li>Use a reliable geolocation service API to map IP addresses to latitude, longitude, and location details (country, region).</li>
      <li>Capture and store the response data in a structured format for ingestion into Azure Sentinel.</li>
    </ul>
  </li>
</ul>

<h3>3. Configure Log Analytics Workspace</h3>
<ul>
  <li>
    <strong>Set Up Custom Log Ingestion</strong><br/>
    <ul>
      <li>Create a custom log source for your geolocation-enriched data within the Log Analytics workspace.</li>
      <li>Verify that logs arrive with accurate fields (e.g., IP address, latitude, longitude, state/province, country).</li>
    </ul>
  </li>
  <li>
    <strong>Validate Ingestion</strong><br/>
    <ul>
      <li>Use Azure Monitor queries (KQL) to confirm that records are populating the workspace correctly.</li>
      <li>Check for any parsing errors or missing fields that may affect your visualizations.</li>
    </ul>
  </li>
</ul>

<h3>4. Map Geodata in Azure Sentinel</h3>
<ul>
  <li>
    <strong>Create Custom Fields</strong><br/>
    <ul>
      <li>Define custom fields in Sentinel or Log Analytics (e.g., “GeoLatitude,” “GeoLongitude”) to store coordinate data.</li>
      <li>Use these fields to plot attack sources on a geographical map visual.</li>
    </ul>
  </li>
  <li>
    <strong>Visualize Attacks & Severity</strong><br/>
    <ul>
      <li>In your Sentinel workbook, layer attack markers on a world map to highlight regions with high brute force activity.</li>
      <li>Optionally, color-code markers by attack frequency or severity for easy threat identification.</li>
    </ul>
  </li>
</ul>

<h2>Conclusion</h2>
<p>
  By integrating <strong>Azure Sentinel</strong> with geolocation data, you can 
  effectively visualize and monitor <strong>global RDP brute force attacks</strong>. This solution allows security teams 
  to pinpoint hotspots, prioritize remediation, and quickly respond to emerging threats. 
  Continual updates to the PowerShell script and Azure workbooks ensure the data remains accurate and actionable.
</p>
