# Gui

# Create GUI window
root = tk.Tk()
root.title("SCAN SENSE")
root.geometry("600x600")
 

# Create a notebook widget
notebook = ttk.Notebook(root)
notebook.pack(fill='both', expand=True)

# Add the main tab to the notebook
main_tab = ttk.Frame(notebook)
notebook.add(main_tab, text="Scan")

# Add the "About ScanSense" tab to the notebook
about_us_tab = ttk.Frame(notebook)
notebook.add(about_us_tab, text="About ScanSense")

# Load the scan image
scan_image = Image.open("scan.png")
scan_image = scan_image.resize((250, 250), Image.LANCZOS)
scan_photo = ImageTk.PhotoImage(scan_image)


# Add the scan image to the main tab
scan_label = tk.Label(main_tab, image=scan_photo)
scan_label.pack(pady=10)

# Create a frame for the IP address label and entry field
ip_frame = tk.Frame(main_tab)
ip_frame.pack(side=tk.TOP, pady=20)


# Create label and entry field for IP address
ip_label = tk.Label(ip_frame, text="Enter the IP address to scan:")
ip_label.pack(side=tk.TOP, padx=10, pady=10)

ip_entry = tk.Entry(ip_frame)
ip_entry.pack(side=tk.TOP, padx=10, pady=10)

# Create label to display the port scan and attack detection results
scan_result_label = tk.Label(main_tab, text="")
scan_result_label.pack()

# Create the buttons and pack them side by side
scan_button = tk.Button(main_tab, text="Scan Ports", command=scan_ports)
scan_button.pack(side=tk.TOP, padx=(20, 5), pady=5)
